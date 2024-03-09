# infinite_craft_itemgiver
Gives you ANY item in infinite craft.

By pasting the code below into your developer console on infinite craft, you can obtain any item.
```
item = prompt("what item should be added?");
var h = new XMLHttpRequest();
h.open( "GET", "https://neal.fun/api/infinite-craft/pair?first=" + item + "&second=none", false ); 
h.send( null );
t = JSON.parse(h.responseText);
b = JSON.parse(localStorage.getItem("infinite-craft-data"));
b["elements"].push({ text: item, emoji: t["emoji"], discovered: t["isNew"] });
localStorage.setItem("infinite-craft-data", JSON.stringify(b));
location.reload();
```

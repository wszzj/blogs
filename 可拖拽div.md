# 可拖拽div

index.html
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <link rel="stylesheet" href="style.css" />
  <title>可拖拽div</title>
</head>
<body>
<div id="xxx"></div>
<script src="main.js"></script>
</body>
</html>
```
style.css
```
div{
  border: 1px solid red;
  position: absolute;
  top: 0;
  left: 0;
  width: 100px;
  height: 100px;
}

*{margin:0; padding: 0;}
```
main.js
```
var dragging = false
var position = null

xxx.addEventListener('mousedown',function(e){
  dragging = true
  position = [e.clientX, e.clientY]
})


document.addEventListener('mousemove', function(e){
  if(dragging === false){return}
  const x = e.clientX
  const y = e.clientY
  const deltaX = x - position[0]
  const deltaY = y - position[1]
  const left = parseInt(xxx.style.left || 0)
  const top = parseInt(xxx.style.top || 0)
  xxx.style.left = left + deltaX + 'px'
  xxx.style.top = top + deltaY + 'px'
  position = [x, y]
})
document.addEventListener('mouseup', function(e){
  dragging = false
})
```

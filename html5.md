## drag&drop
* 被拖动源：   
  `ondragstart()` `ondrag()` `ondragend()`，HTML5为所有的拖动相关事件提供了一个新的属性：e.dataTransfer.数据可以保存在这个属性内，进行被拖动源与拖动目标源之间的交互。  
  
  例如：`ondragstart()`的回调函数内`event.dataTransfer.setData("Text", event.target.id)`通过setData方法设置text属性为拖动源的id，后在`ondrop()`的回调函数内可以通过`event.dataTransfer.getData("Text");`获取到id值，根据id值获取拖动源的数据，进行逻辑操作
   
* 拖动目标源：
  * `ondragenter`：目标对象被源对象拖动着进入  
  * `ondragover`：目标对象被源对象拖动着悬停在上方  
  * `ondragleave`：源对象拖动着离开了目标对象  
  * `ondrop`：源对象拖动着在目标对象上方释放/松手
  
## 懒加载改进方案 `intersection observer` 
  
  `var options = {
    root: document.querySelector('#scrollArea'), 
    rootMargin: '0px', 
    threshold: 1.0
   }`   
   `var callback = (entries, observer) =>{
     entries.forEach(entry =>{   
        entry.***;   
        entry.*****;   
      })   
    }`    
  `var observer = new IntersectionObserver(callback, options);`  
  
  其中options内，root表示监听区域，rootmargin表示基于root的面积加上margin的区域为监听区域，用于拓展监听区域，threshold为0～1之间的值，表示监听内容达到监听区域的百分比值后触发callback方法   
  `var target = document.querySelector('#listItem');`   
`observer.observe(target);`   
需要监听的内容为id=listItem的节点，通过oberser参数的observe方法注册监听

## drag&drop
* 被拖动源：   
  `ondragstart()` `ondrag()` `ondragend()`，HTML5为所有的拖动相关事件提供了一个新的属性：e.dataTransfer.数据可以保存在这个属性内，进行被拖动源与拖动目标源之间的交互。  
  
  例如：`ondragstart()`的回调函数内`event.dataTransfer.setData("Text", event.target.id)`通过setData方法设置text属性为拖动源的id，后在`ondrop()`的回调函数内可以通过`event.dataTransfer.getData("Text");`获取到id值，根据id值获取拖动源的数据，进行逻辑操作
   
* 拖动目标源：
  * `ondragenter`：目标对象被源对象拖动着进入  
  * `ondragover`：目标对象被源对象拖动着悬停在上方  
  * `ondragleave`：源对象拖动着离开了目标对象  
  * `ondrop`：源对象拖动着在目标对象上方释放/松手

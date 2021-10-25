##### 引入component
```
import React, { Component } from "react";
```

##### 继承
```
class Hello extends Component { 
constructor(props){
    super(props); 
    this.state = { msg:'123' }
 }
render() { 
console.log(this.state) // 打印查看 
return ( 
     <div> 
       {/* 在组件中使用私有数据 */}
         <h1>{this.state.msg}</h1> 
     </div> ); 
  } 
}
```

##### export
```
export default Hello;
```
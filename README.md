# Setup
1. Install node.js
2. Create new project with
```command
npx create-react-app my-app
```
3. Delete all file in src/

# Overview
Component มีหลายแบบ
1. React.Component
```javascript
class ShoppingList extends React.Component {
  render() {
    return (
      <div className="shopping-list">
        <h1>Shopping List for {this.props.name}</h1>
        <ul>
          <li>Instagram</li>
          <li>WhatsApp</li>
          <li>Oculus</li>
        </ul>
      </div>
    );
  }
}

// Example usage: <ShoppingList name="Mark" />
```
ถ้าข้อมูลเปลี่ยนมัน render view ให้ใหม่

หรือสามารถเขียนเป็บแบบ JSX ก็ได้
```javascript
return React.createElement('div', {className: 'shopping-list'},
  React.createElement('h1', /* ... h1 children ... */),
  React.createElement('ul', /* ... ul children ... */)
);
```


# Starter Code
เราจะทำ xo game โดยจะมี 3 object
1. Square -> ปุ่มโง่ๆ 
2. Board
3. Game

# วิธีการ passing value และการสร้าง object
เรามี class คือ Board และมี function ในการสร้าง Square โดยเราสามารถเรียกตัวแปรที่ Board ส่งเข้ามาเพื่อสร้าง Square ได้ด้วยการใช้ this.props 

ยกตัวอย่างเล่น 
```javascript
class Square extends React.Component {
  render() {
    return (
      <button className="square">
        {this.props.value}
      </button>
    );
  }
}
```
และ Board สร้าง Square ด้วยการ
```javascript
  renderSquare(i) {
    return <Square value={i} />;
  }
```

# การทำ interactive กับ object
โดยการ set onClick properties
```javascript
onClick={() => console.log('click')}
```
** Note เปลี่ยนจาก XML like เป็น JSX
```javascript
React.createElement('button', {
        className: "square",
        onClick: () => {console.log("Click")}
        }, [this.props.value])
```

# การเก็บ state
มีการเก็บ state โดยใช้ 'this.state' และเปลี่ยน state โดยใช้ 'this.setState()'
การเรียกใช้ setstate จะทำการ re-render child component.
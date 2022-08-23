# Setup
1. Install node.js
2. Create new project with
```
command
npx create-react-app my-app
```
3. Delete all file in src/

# Overview
Component มีหลายแบบ
1. React.Component
```
javascript
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
```
javascript
return React.createElement('div', {className: 'shopping-list'},
  React.createElement('h1', /* ... h1 children ... */),
  React.createElement('ul', /* ... ul children ... */)
);
```

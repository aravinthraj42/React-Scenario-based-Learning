# React-Scenario-based-Learning

**1. How to Display Dynamic HTML Data in React?**************
   
To display dynamic HTML data, you can use the dangerouslySetInnerHTML attribute:
```
const MyComponent = ({ htmlContent }) => (
  <div dangerouslySetInnerHTML={{ __html: htmlContent }} />
);
```
Use this cautiously as it can expose your app to XSS attacks.


**2. How to Send Data from Parent Component to Child Component in React ?**

You can pass data from a parent to a child component using props:
```
export default function App({}) {

  return (
    <div>
      <ParentComponent />
    </div>
  );
}

const ParentComponent = () => {
  const data = "Hello from Parent";
  return <ChildComponent data={data} />;
};

const ChildComponent = ({ data }) => <div>{data}</div>;
```
**3. How to Call Parent Component Method from Child Component in React**
Pass the parent method as a prop to the child component:

```
const ParentComponent = () => {
  const parentMethod = () => alert("Called from Child");

  return <ChildComponent callParentMethod={parentMethod} />;
};

const ChildComponent = ({ callParentMethod }) => (
  <button onClick={callParentMethod}>Call Parent Method</button>
```

**4. How to Access the DOM Element**
You can use useRef in functional components:
```
export default function App() {

  return (
    <div>
      <MyComponent />
    </div>
  );
}


const MyComponent = () => {
  const myRef = useRef(null);

  const focusInput = () => {
    myRef.current.focus();
  };

  return (
    <div>
      <input ref={myRef} type="text" />
      <button onClick={focusInput}>Focus Input</button>
    </div>
  );
};
```

**5. How to Bind Array/Array of Objects to Dropdown in React**
```
export default function App() {

  return (
    <div>
      <MyComponent />
    </div>
  );
}
const MyComponent = () => {
  const options = ["Option 1", "Option 2", "Option 3"];
  
  return (
    <select>
      {options.map(option => (
        <option key={option} value={option}>
          {option}
        </option>
      ))}
    </select>
  );
};
```

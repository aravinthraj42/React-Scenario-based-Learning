# React-Scenario-based-Learning

1. How to Display Dynamic HTML Data in React?
   
To display dynamic HTML data, you can use the dangerouslySetInnerHTML attribute:
```
const MyComponent = ({ htmlContent }) => (
  <div dangerouslySetInnerHTML={{ __html: htmlContent }} />
);
```
Use this cautiously as it can expose your app to XSS attacks.


2. How to Send Data from Parent Component to Child Component in React ?

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

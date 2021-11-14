# react-try

```
<div id="p1">
</div>

<div id="p2">
</div>
```

```
function Person(props) {
  return (
    <div className="person">
    <h1>{props.name}</h1>
    <p>Age : {props.age}</p>
    </div>
  );
}

ReactDOM.render(<Person name="Shohan" age="28" />, document.querySelector('#p1'));

ReactDOM.render(<Person name="Another" age="29" />, document.querySelector('#p2'));
```

# Us

<h2>Table of Contents</h2>

<ol>
  <li><a href="#setup">Setup</a></li>
  <li><a href="#comp">Components</a></li>
  <ul>
    <li><a href="#form">Form</a></li> 
    <li><a href="#textInp">Text Input</a></li>
    <li><a href="#radioInp">Radio Input</a></li>
    <li><a href="#dateInp">Date Input</a></li>
  </ul>
</ol>  

<h2 id="setup">Setup 🖥</h2>

```git clone```

```cd <directory>```

```npm install```

*You have to set environnement variables* in the "backend" directory as follows:

```json
// nodemon.json

{
  "env": {
    "PORT": 4000,
    "DB_HOST": <localhost?>,
    "DB_USER": "root",
    "DB_PASSWORD": <password?>,
    "DB_NAME": "us"
  }
}
```

Work in progress 🔨

<h2 id="comp">Components Doc 📝</h2>

<h3 id="form"><ins>Form</ins></h3>

**v2**

`<Form inputs={exampleForm} onSubmit={submitHandler} /> `

### inputs

<ul>
<li>Type: Array </li>
<li>Required: True</li>
</ul>

### onSubmmit

<ul>
<li>Type: Callback </li>
<li>Required: True</li>
</ul>

<h3 id="textInp"><ins>Text Input</ins></h3>

**v2**

```javascript
<InputTemplate
    placeholder={input.placeholder}
    label={input.label}
    multiline={input.multiline}
    type={input.type}
    security={input.security}
    autoCapitalize={input.autoCapitalize}
    value={input.value}
    onChange={text => changeHandler(text, input)}
    />
```

### id

<ul>
<li>Type: Number </li>
<li>Required: True</li>
</ul>

### render

<ul>
<li>Type: 'text' </li>
<li>Required: True</li>
</ul>

### placeholder

<ul>
<li>Type: String </li>
<li>Required: False</li>
</ul>

### label

<ul>
<li>Type: String </li>
<li>Required: True</li>
</ul>

### multiline

<ul>
<li>Type: Boolean </li>
<li>Required: True</li>
</ul>

### type

<ul>
<li>Type: String ❗️ (https://reactnative.dev/docs/textinput#textcontenttype) </li>
<li>Required: True</li>
</ul>

### security

<ul>
<li>Type: Boolean </li>
<li>Required: False</li>
</ul>

### autoCapitalize

<ul>
<li>Type: String </li>
<li>Required: True</li>
</ul>

### value

<ul>
<li>Type: String </li>
<li>Required: True</li>
</ul>

<h3 id="radioInp"><ins>Radio Input</ins></h3>

**v2**

```javascript
<RadioTemplate
       label={input.label}
       options={input.options}
       value={input.value}
       onChange={option => changeHandler(option, input)}
       />
```

### label

<ul>
<li>Type: String </li>
<li>Required: True</li>
</ul>

### options

<ul>
<li>Type: Array </li>
<li>Required: True</li>
</ul>

### value

<ul>
<li>Type: String </li>
<li>Required: True</li>
</ul>

<h3 id="dateInp"><ins>Date Input</ins></h3>

**v2**

```javascript
<DatePickerTemplate
       label={input.label}
       value={input.value}
       onChange={date => changeHandler(date, input)}
       />
```

### label

<ul>
<li>Type: String </li>
<li>Required: True</li>
</ul>

### value

<ul>
<li>Type: String </li>
<li>Required: True</li>
</ul>

### Example:

```javascript
const exampleForm = [
  {
    id: 1,
    render: 'text',
    placeholder: 'Write here...',
    label: 'Email',
    multiline: false,
    type: 'emailAddress',
    security: false,
    autoCapitalize: 'none',
    value: ''
  },
  {
    id: 2,
    render: 'text',
    placeholder: 'Write here...',
    label: 'Password',
    multiline: false,
    type: 'password',
    security: true,
    autoCapitalize: 'none',
    value: ''
  },
  {
    id: 3,
    render: 'radio',
    label: 'Gender',
    options: ['Male', 'Female', 'Other'],
    value: 'Other'
  },
  {
    id: 4,
    render: 'date',
    label: 'Date of birth',
    value: new Date()
  }
];

const App = () => {
  const submitHandler = data => console.log(data);

  return (
    <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
      <FormTemplate inputs={exampleForm} onSubmit={submitHandler} />
    </View>
  );
};
```




# igroot-editor

igroot-editor is a react markdown editor

# Getting Started

### Install

```js
npm install igroot-editor -S
```

### Using igroot-editor

```js
import React, { Component } from 'react'
import ReactDOM from 'react-dom'
import Editor from 'igroot-editor'

class App extends Component {
  constructor() {
    super()
    this.state = {
      value: ''
    }
  }

  handleChange(value) {
    this.setState({
      value
    })
  }

  render() {
    const { value } = this.state
    return (
      <Editor value={value} onChange={this.handleChange.bind(this)} preview />
    )
  }
}

ReactDOM.render(<Editor />, document.getElementById('container'))
```

### Api

#### props

| name        | type    | default       | description             |
| ----------- | ------- | ------------- | ----------------------- |
| placeholder | String  | 请输入内容... | 占位文本                |
| value       | String  | -             | 输入框内容              |
| preview     | Boolean | false         | 默认开启编辑            |
| viewOnly    | Boolean | false         | 只渲染 md，不渲染编辑器 |
| lineNum     | Boolean | true          | 是否显示行号            |

#### events

| name     | type        | default | description    |
| -------- | ----------- | ------- | -------------- |
| onChange | function(e) | -       | 内容改变时回调 |
| onSave   | function(e) | -       | 保存时回调     |

#### hot key

| name   | description  |
| ------ | ------------ |
| tab    | 两个空格缩进 |
| ctrl+s | 保存         |
| ctrl+z | 上一步       |
| ctrl+y | 下一步       |

## 目录结构

```
├── LICENSE
├── README.md
├── __mocks__
│   ├── fileMock.js
│   └── styleMock.js
├── __test__   测试用例
│   ├── editor
│   │   └── index.spec.js
│   ├── helper
│   │   └── insertText.spec.js
│   └── main.spec.js
├── build   构建文件目录
│   ├── webpack.base.config.js
│   ├── webpack.dev.config.js
│   ├── webpack.dist.config.js
│   └── webpack.prod.config.js
├── dist   构建后的文件
│   ├── index.js
│   └── static
│       └── fonts
│           ├── iconfont.2326a17b.ttf
│           ├── iconfont.61c479ed.eot
│           ├── iconfont.9141b033.woff
│           └── iconfont.9443acb4.svg
├── doc
│   └── UPDATELOG.md
├── example    本地测试应用
│   ├── index.html
│   ├── index.js
│   └── src
│       ├── app.jsx
│       ├── app.module.scss
│       └── editor.jsx
├── jest.config.js
├── package.json
├── playground   本地测试构建后的文件
│   ├── index.js
│   └── static
│       └── fonts
│           ├── iconfont.2326a17b.ttf
│           ├── iconfont.61c479ed.eot
│           ├── iconfont.9141b033.woff
│           └── iconfont.9443acb4.svg
├── src   源码目录
│   ├── editor
│   │   ├── index.jsx
│   │   └── index.scss
│   ├── fonts
│   │   ├── iconfont.css
│   │   ├── iconfont.eot
│   │   ├── iconfont.svg
│   │   ├── iconfont.ttf
│   │   ├── iconfont.woff
│   │   └── iconfont.woff2
│   ├── helpers
│   │   ├── highlight.js
│   │   ├── insertText.js
│   │   ├── keydownListen.js
│   │   └── marked.js
│   └── main.js
├── test
│   └── setupTests.js
├── yarn-error.log
└── yarn.lock
```

## 技术栈

react + highlight.js + marked

## 发布

```
yarn publish
```

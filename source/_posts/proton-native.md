---
title: Build the GUI with proton react-nativ
date: 2018-05-30 10:15:01
tags: nodejs gui proton react
---


Create native desktop application through a react-native platform

# background
Build the desktop applicaiton based on the node.js platform have some library we can use, the electron is the pioneer and Atom and Visual Studio Code are the good example, but the electron based application is not friendly for the mini-apps, and react-native is the good choice for the universal application interface for the web, mobile and DESKTOP.

Proton-Native is the library to build the desktop application based on the react-native library and libui, can build the same GUI application to support the Windows, Linux and OSX, same code logic, same development lifecyle and deployment to different user inferface platform.


# Get started
[proton-native document](https://proton-native.js.org)
[proton-native github](https://github.com/kusti8/proton-native)
[proton-native example](https://github.com/kusti8/progon-native/examples/)

## build system pre-requist
you need nodejs version 8 or newer
and the build system for the os
windows depends on the visual studio
linux need libgtk-3 build-essential
OSX need xcode-cli

## react-native cli

npm install -g create-proton-app
create-proton-app my-app
cd my-app && npm run-start

modify the index.js to customize your app

## package
depends on the electron-builder, we can package the app on the Linux and OSX, windows is not supported now.

to build the app: npm build
to builde the app: npm run dist

## manually prepare the app development

. development bundler tools babel babel-cli babel-prepset-env babel-preset-react babel-preset-stage-0

create the .babelrc: 
{
    "presets": [
        "env",
        "statge-0",
        "react"
    ]
}

add the following script in the package.json

"start": "babel-node index.js"

and then run the app with npm start
# example of Hello-Proton

```
//index.js
import React, { Component } from 'react'
import {
    render, App, Window
} from 'proton-native'

class Hello {
    render() {
        return (
            <App>
                <Window title='Hello Proton' 
                    size={{{w: 400, h: 300}
                />
            <App>
        )
    }
}
render(<Hello />)
```
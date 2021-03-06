# CKEditor for Next.js 

Custom CKEditor component for Next.js apps.

This package contains:

- classic editor
- heading (h1, h2, h3 and paragraph)
- font properties (color, size, family, background color, bold, italic, underline & aligment)
- image upload (base64 & url)
- lists
- blockquotes
- tables
- code block
- undo & redo

## Getting started 

- Install the modules:

```sh
npm i @jorge-salgado/ckeditor5-next.js
npm i @ckeditor/ckeditor5-react
```

- Create the new component:

```js
import React, { Component } from 'react';
import Editor from '@jorge-salgado/ckeditor5-next.js';
import { CKEditor } from '@ckeditor/ckeditor5-react'

function EditorCK  ({ data, onChange })  {
        return (
            <CKEditor
                editor={ Editor }
                data={data}
                onChange={ ( event, editor ) => {
                    const data = editor.getData();
                    onChange(data)
                }}
            />
    );
}

export default EditorCK

```	

- Use the component:

```js
import React, { useState } from "react";
import dynamic from 'next/dynamic';
const EditorCK = dynamic(() => import('../../../components/Blog/EditorCK'), {ssr: false});

const App = () => (

    const [data, setData] = useState("");

    return(

        <div>
            <EditorCK 
                data={data}
                onChange={(data) => setData(data)}
            />
        </div>

    )
);

```	

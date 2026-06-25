## NextJs API---> Params, Body, FormData

### Search Params

![](https://imgur.com/jCj0iS5.png)

```bash
import { NextResponse } from "next/server";


export async function GET(request:Request) {

    const {searchParams} = new URL(request.url);
    let id = searchParams.get('id');
    
    return NextResponse.json(
        {status: "Success response", message: id},
        {status: 200}
    )
}
```
---


### Multiple Parameter

![](https://imgur.com/djqGudL.png)

```bash
import { NextResponse } from "next/server";


export async function GET(request:Request) {

    const {searchParams} = new URL(request.url);
    let name = searchParams.get('name');
    let email = searchParams.get('email');
    let designation = searchParams.get('designation');
    
    return NextResponse.json(
        {status: "Success response", message: {name, email, designation}},
        {status: 200}
    )
}
```
---

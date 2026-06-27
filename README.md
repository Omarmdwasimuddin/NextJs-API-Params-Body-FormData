## NextJs API---> Params, Body, FormData

### Search Params

![](https://imgur.com/jCj0iS5.png)

```bash
import { NextRequest, NextResponse } from "next/server";


export async function GET(request:NextRequest) {

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
import { NextRequest, NextResponse } from "next/server";


export async function GET(request:NextRequest) {

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

### Body

![](https://imgur.com/KjVH1v6.png)

```bash
import { NextRequest, NextResponse } from "next/server";

export async function POST(request:NextRequest) {

    const requestBody = await request.json()
    
    return NextResponse.json(
        {status: "Success response", message: requestBody},
        {status: 200}
    )
}
```

#### particular value response
![](https://imgur.com/CxZjzSm.png)

```bash
import { NextRequest, NextResponse } from "next/server";

export async function POST(request:NextRequest) {

    const requestBody = await request.json()
    
    return NextResponse.json(
        {status: "Success response", message: requestBody['name']},
        {status: 200}
    )
}
```

---

### Form Data

![](https://imgur.com/ykBF7fu.png)

```bash
import { NextRequest, NextResponse } from "next/server";

export async function PUT(request:NextRequest) {

    let formData = await request.formData();
    let mobile = formData.get('Mobile');
    let email = formData.get('Email');
    let designation = formData.get('Designation');
    
    return NextResponse.json(
        {status: "Success response", message: {mobile, email, designation}},
        {status: 200}
    )
}
```
---

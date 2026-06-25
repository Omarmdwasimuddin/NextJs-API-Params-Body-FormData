## NextJs API---> Params, Body, FormData

### Search Params

![]()

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

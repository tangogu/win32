---
Description: Requests to return generic object data that describes an object in the .vsglog file for the specified event and in the specified format.
MS-HAID: vspixengine.IGenericBufferDataRequest\_RequestAsync\_DumperType\_EventID\_DWORD\_IGenericBufferDataCallback\_ptr\_DWORD\_DWORD
MSHAttr:
- PreferredSiteName:MSDN
- PreferredLib:/library/windows/desktop
title: IGenericBufferDataRequest::RequestAsync method
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# <span id="vspixengine.igenericbufferdatarequest_requestasync_dumpertype_eventid_dword_igenericbufferdatacallback_ptr_dword_dword"></span>IGenericBufferDataRequest::RequestAsync method

Requests to return generic object data that describes an object in the .vsglog file for the specified event and in the specified format.

## Syntax


```C++
);
```

## Parameters

*dumperType*   
The specified format of the textual representation of the object (HTML, XML, etc.)

*eventID*   
The specified event to match the buffer's content to (for example, a render target could change over time).

*RequestedDataUID*   
The address of the specified object.

*requestCallback*   
The address of callback used to notify the host of results.

*requestCookie*   
A cookie that uniquely identifies the request, and can be used to signal for it to be cancelled.

*progressIntervalMsecs*   
Not used.

## Return value

If this method succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Requirements

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><p>Header</p></td><td>Vspixengine.h</td></tr></tbody></table>

## <span id="see_also"></span>See also

[**IGenericBufferDataRequest**](https://msdn.microsoft.com/library/windows/desktop/mt422684)

 

 



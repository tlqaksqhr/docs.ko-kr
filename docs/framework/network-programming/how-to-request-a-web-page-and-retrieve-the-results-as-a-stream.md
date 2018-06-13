---
title: '방법: 웹 페이지 요청 및 결과를 스트림으로 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 31856e7fc7136b3bdb8fab9fdf8185de32a3007a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395215"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="dd68e-102">방법: 웹 페이지 요청 및 결과를 스트림으로 검색</span><span class="sxs-lookup"><span data-stu-id="dd68e-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>
<span data-ttu-id="dd68e-103">이 예제에서는 웹 페이지를 요청하고 스트림에서 결과를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd68e-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd68e-104">예</span><span class="sxs-lookup"><span data-stu-id="dd68e-104">Example</span></span>  
  
```csharp  
WebClient myClient = new WebClient();  
Stream response = myClient.OpenRead("http://www.contoso.com/index.htm");  
// The stream data is used here.  
response.Close();  
```  
  
```vb  
Dim myClient As WebClient = New WebClient()  
Dim response As Stream = myClient.OpenRead("http://www.contoso.com/index.htm")  
' The stream data is used here.  
response.Close()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dd68e-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="dd68e-105">Compiling the Code</span></span>  
 <span data-ttu-id="dd68e-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dd68e-106">This example requires:</span></span>  
  
-   <span data-ttu-id="dd68e-107"><xref:System.IO> 및 <xref:System.Net> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="dd68e-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd68e-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd68e-108">See Also</span></span>  
 [<span data-ttu-id="dd68e-109">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="dd68e-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)

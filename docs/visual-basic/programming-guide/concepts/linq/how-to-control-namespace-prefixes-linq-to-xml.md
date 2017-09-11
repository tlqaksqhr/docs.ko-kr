---
title: "방법: Namespace 접두사 제어 (Visual Basic) (LINQ to XML) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 87db9e5384bee835ca4fde141765eabf9a7cfedb
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="afc2e-102">방법: 네임스페이스 접두사 제어(Visual Basic)(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="afc2e-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="afc2e-103">이 항목에서는 네임스페이스 접두사를 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="afc2e-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afc2e-104">예제</span><span class="sxs-lookup"><span data-stu-id="afc2e-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="afc2e-105">설명</span><span class="sxs-lookup"><span data-stu-id="afc2e-105">Description</span></span>  
 <span data-ttu-id="afc2e-106">이 예제에서는 두 네임스페이스를 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="afc2e-106">This example declares two namespaces.</span></span> <span data-ttu-id="afc2e-107">지정 하는 `http://www.adventure-works.com` 네임 스페이스가 `aw`, 하는 `www.fourthcoffee.com` 네임 스페이스의 접두사에 `fc`합니다.</span><span class="sxs-lookup"><span data-stu-id="afc2e-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="afc2e-108">코드</span><span class="sxs-lookup"><span data-stu-id="afc2e-108">Code</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="afc2e-109">설명</span><span class="sxs-lookup"><span data-stu-id="afc2e-109">Comments</span></span>  
 <span data-ttu-id="afc2e-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="afc2e-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="afc2e-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="afc2e-111">See Also</span></span>  
 [<span data-ttu-id="afc2e-112">XML 네임 스페이스 (Visual Basic) 작업</span><span class="sxs-lookup"><span data-stu-id="afc2e-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)

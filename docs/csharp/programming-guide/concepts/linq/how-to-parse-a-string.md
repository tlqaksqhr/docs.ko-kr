---
title: "방법: 문자열 구문 분석(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 37e09885b00830f319a829e900f33927498df0e3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-parse-a-string-c"></a><span data-ttu-id="e7b02-102">방법: 문자열 구문 분석(C#)</span><span class="sxs-lookup"><span data-stu-id="e7b02-102">How to: Parse a String (C#)</span></span>
<span data-ttu-id="e7b02-103">이 항목에서는 C#에서 문자열의 구문을 분석하여 XML 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e7b02-103">This topic shows how to parse a string to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7b02-104">예제</span><span class="sxs-lookup"><span data-stu-id="e7b02-104">Example</span></span>  
 <span data-ttu-id="e7b02-105">다음 C# 코드에서는 문자열의 구문을 분석하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e7b02-105">The following C# code shows how to parse a string.</span></span>  
  
```csharp  
XElement contacts = XElement.Parse(  
    @"<Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type=""home"">206-555-0144</Phone>  
            <Phone type=""work"">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type=""mobile"">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>");  
Console.WriteLine(contacts);  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7b02-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7b02-106">See Also</span></span>  
 [<span data-ttu-id="e7b02-107">XML 구문 분석(C#)</span><span class="sxs-lookup"><span data-stu-id="e7b02-107">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)

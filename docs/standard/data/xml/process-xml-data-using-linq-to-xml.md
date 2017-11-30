---
title: "LINQ to XML을 사용하여 XML 데이터 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 059d6b9d-63f7-4011-9ba8-8406f0bbae7d
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a6b7a3c452d6b29145b8a2e7b1d2a1e824aaf508
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="process-xml-data-using-linq-to-xml"></a><span data-ttu-id="6f040-102">LINQ to XML을 사용하여 XML 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="6f040-102">Process XML Data Using LINQ to XML</span></span>
<span data-ttu-id="6f040-103">LINQ to XML은 XML 데이터를 처리하기 위한 .NET Framework 버전 3.5의 새 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="6f040-103">LINQ to XML is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="6f040-104">LINQ to XML을 사용하여 XML 문서 쿼리, 수정, 작성, 저장, serialize 등 XML 데이터에 대한 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f040-104">LINQ to XML allows developers to do everything they would expect with XML data: querying, modifying, creating, saving, and serializing XML documents.</span></span> <span data-ttu-id="6f040-105">이 가운데 가장 실질적인 장점은 쿼리 및 작성 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6f040-105">The real advantages lie in the query and creation capabilities.</span></span>  
  
 <span data-ttu-id="6f040-106">LINQ to XML의 쿼리는 XPath 또는 XQuery보다는 SQL에 유사한 구문을 사용하여 간결하고 표현이 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="6f040-106">Queries in LINQ to XML are succinct and expressive, using syntax more similar to SQL than to XPath or XQuery.</span></span> <span data-ttu-id="6f040-107">쿼리 결과가 요소 또는 특성의 컬렉션으로 반환되어 XElement 개체의 매개 변수로 사용될 수 있으므로 XML 트리는 한 모형에서 다른 모형으로 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f040-107">Because query results can be returned as collections of elements or attributes and can be used as parameters for XElement objects, XML trees can be easily transformed from one shape to another.</span></span>  
  
 <span data-ttu-id="6f040-108">LINQ to XML은 .NET Framework 버전 3.5의 LINQ(Language-Integrated Query) 기술을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6f040-108">LINQ to XML leverages the language-integrated query (LINQ) technology in the .NET Framework version 3.5.</span></span> <span data-ttu-id="6f040-109">LINQ는 강력한 쿼리 기능을 제공하기 위해 C# 및 Visual Basic의 언어 구문을 확장하여 모든 데이터 저장소를 잠재적으로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f040-109">LINQ extends the language syntax of C# and Visual Basic to provide powerful query capabilities that can be extended to potentially any data store.</span></span>  
  
 <span data-ttu-id="6f040-110">참조 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) 해당 사용 및 참조에 대 한 자세한 내용은 대 한 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) LINQ 프레임 워크에 대 한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="6f040-110">See [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) for a detailed discussion of its use, and see [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) for an overview of the LINQ framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f040-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f040-111">See Also</span></span>  
 <xref:System.Xml.Linq>  
 <xref:System.Linq>  
 [<span data-ttu-id="6f040-112">LINQ to XML과 DOM 비교</span><span class="sxs-lookup"><span data-stu-id="6f040-112">LINQ to XML vs. DOM</span></span>](http://msdn.microsoft.com/library/19b5ed02-feb2-455a-8897-f7f0fd76aca3)  
 [<span data-ttu-id="6f040-113">LINQ to XML과 기타 XML 기술 비교</span><span class="sxs-lookup"><span data-stu-id="6f040-113">LINQ to XML vs. Other XML Technologies</span></span>](http://msdn.microsoft.com/library/7ba1eecf-f09a-42de-bc80-22ca5b2e42d3)

---
title: "샘플 XML 파일: 일반적인 구매 주문에는 Namespace3 | Microsoft 문서"
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
ms.assetid: 38260901-c9f9-4240-9cbf-652c8b05021d
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
ms.openlocfilehash: dbb6adbde15f129fd4413ef111d60b767cb25174
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="sample-xml-file-typical-purchase-order-in-a-namespace"></a><span data-ttu-id="5fcc8-102">샘플 XML 파일: 네임스페이스에서 일반적인 구매 주문</span><span class="sxs-lookup"><span data-stu-id="5fcc8-102">Sample XML File: Typical Purchase Order in a Namespace</span></span>
<span data-ttu-id="5fcc8-103">다음 XML 파일은 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 설명서의 다양한 예제에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fcc8-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] documentation.</span></span> <span data-ttu-id="5fcc8-104">이 파일은 일반적인 구매 주문입니다.</span><span class="sxs-lookup"><span data-stu-id="5fcc8-104">This file is a typical purchase order.</span></span> <span data-ttu-id="5fcc8-105">XML은 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fcc8-105">The XML is in a namespace.</span></span>  
  
## <a name="purchaseorderinnamespacexml"></a><span data-ttu-id="5fcc8-106">PurchaseOrderInNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="5fcc8-106">PurchaseOrderInNamespace.xml</span></span>  
  
```xml  
<?xml version="1.0"?>  
<aw:PurchaseOrder  
    aw:PurchaseOrderNumber="99503"  
    aw:OrderDate="1999-10-20"  
    xmlns:aw="http://www.adventure-works.com">  
  <aw:Address aw:Type="Shipping">  
    <aw:Name>Ellen Adams</aw:Name>  
    <aw:Street>123 Maple Street</aw:Street>  
    <aw:City>Mill Valley</aw:City>  
    <aw:State>CA</aw:State>  
    <aw:Zip>10999</aw:Zip>  
    <aw:Country>USA</aw:Country>  
  </aw:Address>  
  <aw:Address aw:Type="Billing">  
    <aw:Name>Tai Yee</aw:Name>  
    <aw:Street>8 Oak Avenue</aw:Street>  
    <aw:City>Old Town</aw:City>  
    <aw:State>PA</aw:State>  
    <aw:Zip>95819</aw:Zip>  
    <aw:Country>USA</aw:Country>  
  </aw:Address>  
  <aw:DeliveryNotes>Please leave packages in shed by driveway.</aw:DeliveryNotes>  
  <aw:Items>  
    <aw:Item aw:PartNumber="872-AA">  
      <aw:ProductName>Lawnmower</aw:ProductName>  
      <aw:Quantity>1</aw:Quantity>  
      <aw:USPrice>148.95</aw:USPrice>  
      <aw:Comment>Confirm this is electric</aw:Comment>  
    </aw:Item>  
    <aw:Item aw:PartNumber="926-AA">  
      <aw:ProductName>Baby Monitor</aw:ProductName>  
      <aw:Quantity>2</aw:Quantity>  
      <aw:USPrice>39.98</aw:USPrice>  
      <aw:ShipDate>1999-05-21</aw:ShipDate>  
    </aw:Item>  
  </aw:Items>  
</aw:PurchaseOrder>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5fcc8-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5fcc8-107">See Also</span></span>  
 [<span data-ttu-id="5fcc8-108">샘플 XML 문서(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="5fcc8-108">Sample XML Documents (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)

---
title: "샘플 XML 문서 (LINQ to XML) | Microsoft 문서"
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
ms.assetid: a734cc4e-d95d-4631-91a2-81618c8ad894
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
ms.openlocfilehash: df50a49831031edaa1ac349efa9a5ff9b6688dd8
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="sample-xml-documents-linq-to-xml"></a><span data-ttu-id="96e99-102">샘플 XML 문서(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="96e99-102">Sample XML Documents (LINQ to XML)</span></span>
<span data-ttu-id="96e99-103">다음 예제 파일 코드 샘플 및 전체에서 코드 조각에 사용 되는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="96e99-103">The following example files are used in the code samples and code snippets throughout the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96e99-104">이 문서에 사용된 예제 회사, 조직, 제품, 도메인 이름, 전자 메일 주소, 로고, 사람, 장소 및 이벤트는 실제 데이터가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="96e99-104">The example companies, organizations, products, domain names, e-mail addresses, logos, people, places, and events depicted herein are fictitious.</span></span> <span data-ttu-id="96e99-105">어떠한 실제 회사, 조직, 제품, 도메인 이름, 전자 메일 주소, 로고, 사람, 장소 또는 이벤트와도 연관시킬 의도가 없으며 그렇게 유추해서도 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96e99-105">No association with any real company, organization, product, domain name, e-mail address, logo, person, places, or events is intended or should be inferred.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96e99-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="96e99-106">In This Section</span></span>  
  
|<span data-ttu-id="96e99-107">항목</span><span class="sxs-lookup"><span data-stu-id="96e99-107">Topic</span></span>|<span data-ttu-id="96e99-108">설명</span><span class="sxs-lookup"><span data-stu-id="96e99-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="96e99-109">샘플 XML 파일: 일반적인 구매 주문(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="96e99-109">Sample XML File: Typical Purchase Order (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)|<span data-ttu-id="96e99-110">일반적인 구매 주문이 포함된 XML 문서</span><span class="sxs-lookup"><span data-stu-id="96e99-110">An XML document that contains a typical purchase order.</span></span>|  
|[<span data-ttu-id="96e99-111">샘플 XML 파일: 네임스페이스에서 일반적인 구매 주문</span><span class="sxs-lookup"><span data-stu-id="96e99-111">Sample XML File: Typical Purchase Order in a Namespace</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md)|<span data-ttu-id="96e99-112">일반적인 구매 주문이 포함된 네임스페이스의 XML 문서</span><span class="sxs-lookup"><span data-stu-id="96e99-112">An XML document in a namespace that contains a typical purchase order.</span></span>|  
|[<span data-ttu-id="96e99-113">샘플 XML 파일: 여러 구매 주문(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="96e99-113">Sample XML File: Multiple Purchase Orders (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)|<span data-ttu-id="96e99-114">여러 구매 주문이 포함된 XML 문서</span><span class="sxs-lookup"><span data-stu-id="96e99-114">An XML document that contains multiple purchase orders.</span></span>|  
|[<span data-ttu-id="96e99-115">샘플 XML 파일: 네임스페이스에서 여러 구매 주문</span><span class="sxs-lookup"><span data-stu-id="96e99-115">Sample XML File: Multiple Purchase Orders in a Namespace</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md)|<span data-ttu-id="96e99-116">여러 구매 주문이 포함된 네임스페이스의 XML 문서</span><span class="sxs-lookup"><span data-stu-id="96e99-116">An XML document in a namespace that contains multiple purchase orders.</span></span>|  
|[<span data-ttu-id="96e99-117">샘플 XML 파일: 테스트 구성(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="96e99-117">Sample XML File: Test Configuration (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md)|<span data-ttu-id="96e99-118">의사(pseudo) 테스트 구성 데이터가 포함된 XML 문서</span><span class="sxs-lookup"><span data-stu-id="96e99-118">An XML document that contains some pseudo test configuration data.</span></span>|  
|[<span data-ttu-id="96e99-119">샘플 XML 파일: 네임스페이스에서 테스트 구성</span><span class="sxs-lookup"><span data-stu-id="96e99-119">Sample XML File: Test Configuration in a Namespace</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md)|<span data-ttu-id="96e99-120">의사(pseudo) 테스트 구성 데이터가 포함된 네임스페이스의 XML 문서</span><span class="sxs-lookup"><span data-stu-id="96e99-120">An XML document in a namespace that contains some pseudo test configuration data.</span></span>|  
|[<span data-ttu-id="96e99-121">샘플 XML 파일: Customers 및 Orders(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="96e99-121">Sample XML File: Customers and Orders (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md)|<span data-ttu-id="96e99-122">고객과 주문이 포함된 XML 문서</span><span class="sxs-lookup"><span data-stu-id="96e99-122">An XML document that contains customers and orders.</span></span>|  
|[<span data-ttu-id="96e99-123">샘플 XSD 파일: Customers 및 Orders</span><span class="sxs-lookup"><span data-stu-id="96e99-123">Sample XSD File: Customers and Orders</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md)|<span data-ttu-id="96e99-124">Xml XSD (스키마 정의) 유효성을 검사 하는 [샘플 XML 파일: Customers 및 Orders (LINQ to XML)](http://msdn.microsoft.com/library/26790c41-5976-4558-a096-d0f67bfc4d92)합니다.</span><span class="sxs-lookup"><span data-stu-id="96e99-124">An Xml Schema Definition (XSD) that validates the [Sample XML File: Customers and Orders (LINQ to XML)](http://msdn.microsoft.com/library/26790c41-5976-4558-a096-d0f67bfc4d92).</span></span>|  
|[<span data-ttu-id="96e99-125">샘플 XML 파일: 네임스페이스의 Customers 및 Orders</span><span class="sxs-lookup"><span data-stu-id="96e99-125">Sample XML File: Customers and Orders in a Namespace</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-in-a-namespace.md)|<span data-ttu-id="96e99-126">고객과 주문이 포함된 네임스페이스의 XML 문서</span><span class="sxs-lookup"><span data-stu-id="96e99-126">An XML document in a namespace that contains customers and orders.</span></span>|  
|[<span data-ttu-id="96e99-127">샘플 XML 파일: 숫자 데이터(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="96e99-127">Sample XML File: Numerical Data (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md)|<span data-ttu-id="96e99-128">합계를 구하고 그룹화하는 데 적합한 데이터가 포함된 XML 문서</span><span class="sxs-lookup"><span data-stu-id="96e99-128">An XML document that contains data suitable for summing and grouping.</span></span>|  
|[<span data-ttu-id="96e99-129">샘플 XML 파일: 네임스페이스의 숫자 데이터</span><span class="sxs-lookup"><span data-stu-id="96e99-129">Sample XML File: Numerical Data in a Namespace</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md)|<span data-ttu-id="96e99-130">합계를 구하고 그룹화하는 데 적합한 데이터가 포함된 네임스페이스의 XML 문서</span><span class="sxs-lookup"><span data-stu-id="96e99-130">An XML document in a namespace that contains data suitable for summing and grouping.</span></span>|  
|[<span data-ttu-id="96e99-131">샘플 XML 파일: Books(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="96e99-131">Sample XML File: Books (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)|<span data-ttu-id="96e99-132">책의 카탈로그가 포함된 XML 문서</span><span class="sxs-lookup"><span data-stu-id="96e99-132">An XML document that contains a catalog of books.</span></span>|  
|[<span data-ttu-id="96e99-133">샘플 XML 파일: 통합된 구매 주문</span><span class="sxs-lookup"><span data-stu-id="96e99-133">Sample XML File: Consolidated Purchase Orders</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-consolidated-purchase-orders.md)|<span data-ttu-id="96e99-134">다른 네임스페이스에 있는 구매 주문이 포함된 XML 문서</span><span class="sxs-lookup"><span data-stu-id="96e99-134">Presents an XML document that contains purchase orders that are in different namespaces.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96e99-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96e99-135">See Also</span></span>  
 [<span data-ttu-id="96e99-136">프로그래밍 가이드 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96e99-136">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)

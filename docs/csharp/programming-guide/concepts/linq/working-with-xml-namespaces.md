---
title: "XML 네임스페이스 작업(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 05cf4dc7-7b25-40f0-abc9-1bc35de4b48a
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 98627e6944f774bb74f705c8c8607e856e1c1195
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="working-with-xml-namespaces-c"></a><span data-ttu-id="84c03-102">XML 네임스페이스 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="84c03-102">Working with XML Namespaces (C#)</span></span>
<span data-ttu-id="84c03-103">이 단원의 항목에서는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서 네임스페이스를 지원하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84c03-103">The topics in this section describe how [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] supports namespaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84c03-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="84c03-104">In This Section</span></span>  
  
|<span data-ttu-id="84c03-105">항목</span><span class="sxs-lookup"><span data-stu-id="84c03-105">Topic</span></span>|<span data-ttu-id="84c03-106">설명</span><span class="sxs-lookup"><span data-stu-id="84c03-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="84c03-107">네임스페이스 개요(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="84c03-107">Namespaces Overview (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)|<span data-ttu-id="84c03-108">이 항목에서는 네임스페이스, <xref:System.Xml.Linq.XName> 클래스 및 <xref:System.Xml.Linq.XNamespace> 클래스에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="84c03-108">This topic introduces namespaces, the <xref:System.Xml.Linq.XName> class, and the <xref:System.Xml.Linq.XNamespace> class.</span></span>|  
|[<span data-ttu-id="84c03-109">방법: 네임스페이스로 문서 만들기(C#)(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="84c03-109">How to: Create a Document with Namespaces (C#) (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-create-a-document-with-namespaces-linq-to-xml.md)|<span data-ttu-id="84c03-110">네임스페이스를 사용하여 문서를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="84c03-110">Shows how to create documents with namespaces.</span></span>|  
|[<span data-ttu-id="84c03-111">방법: 네임스페이스 접두사 제어(C#)(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="84c03-111">How to: Control Namespace Prefixes (C#) (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-control-namespace-prefixes-linq-to-xml.md)|<span data-ttu-id="84c03-112">네임스페이스 특성을 XML 트리에 삽입하여 네임스페이스 접두사를 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="84c03-112">Shows how to control namespace prefixes by inserting namespace attributes into the XML tree.</span></span>|  
|[<span data-ttu-id="84c03-113">C#에서 기본 네임스페이스 범위</span><span class="sxs-lookup"><span data-stu-id="84c03-113">Scope of Default Namespaces in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/scope-of-default-namespaces.md)|<span data-ttu-id="84c03-114">기본 네임스페이스의 XML에 대한 쿼리를 작성하는 적절한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="84c03-114">Demonstrates the appropriate way to write queries for XML in the default namespace.</span></span>|  
|[<span data-ttu-id="84c03-115">방법: 네임스페이스에서 XML로 쿼리 작성(C#)</span><span class="sxs-lookup"><span data-stu-id="84c03-115">How to: Write Queries on XML in Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-write-queries-on-xml-in-namespaces.md)|<span data-ttu-id="84c03-116">C# LINQ to XML 쿼리에서 XML 네임스페이스를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="84c03-116">Demonstrates how to specify XML namespaces in C# LINQ to XML queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84c03-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84c03-117">See Also</span></span>  
 [<span data-ttu-id="84c03-118">프로그래밍 가이드(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="84c03-118">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)


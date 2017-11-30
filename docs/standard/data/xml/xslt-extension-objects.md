---
title: "XSLT 확장명 개체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4ebdbad-087c-4cfe-acc0-17c48142f81a
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2916f7da6b990cddef9b86559a71b5206351d558
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xslt-extension-objects"></a><span data-ttu-id="e7eda-102">XSLT 확장명 개체</span><span class="sxs-lookup"><span data-stu-id="e7eda-102">XSLT Extension Objects</span></span>
<span data-ttu-id="e7eda-103">확장명 개체를 사용하여 스타일시트의 기능을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-103">Extension objects are used to extend the functionality of style sheets.</span></span> <span data-ttu-id="e7eda-104">확장 개체는 <xref:System.Xml.Xsl.XsltArgumentList> 클래스를 사용하여 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-104">Extension objects are maintained by the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span>  
  
 <span data-ttu-id="e7eda-105">포함 스크립트를 사용하는 대신 확장 개체를 사용하면 다음과 같은 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-105">The following are advantages to using an extension object rather than embedded script:</span></span>  
  
-   <span data-ttu-id="e7eda-106">클래스 캡슐화 및 재사용에 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-106">Provides better encapsulation and reuse of classes.</span></span>  
  
-   <span data-ttu-id="e7eda-107">스타일시트를 더 작게 유지하고 보다 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-107">Allows style sheets to be smaller and more maintainable.</span></span>  
  
 <span data-ttu-id="e7eda-108"><xref:System.Xml.Xsl.XsltArgumentList> 메서드를 사용하여 <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> 개체에 XSLT 확장 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-108">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> object using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="e7eda-109">이 때 정규화된 이름과 네임스페이스 URI가 확장 개체와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-109">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7eda-110"><xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> 메서드를 호출하려면 FullTrust 권한 집합이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-110">The FullTrust permission set is required to call the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="e7eda-111">자세한 내용은 참조 [코드 액세스 보안](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03) 및 [NIB: 명명 된 권한 집합](http://msdn.microsoft.com/en-us/08250d67-c99d-4ab0-8d2b-b0e12019f6e3)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-111">For more information, see [Code Access Security](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03) and [NIB: Named Permission Sets](http://msdn.microsoft.com/en-us/08250d67-c99d-4ab0-8d2b-b0e12019f6e3).</span></span>  
  
 <span data-ttu-id="e7eda-112">확장 개체에서 반환된 데이터 형식은 네 가지 기본 XPath 데이터 형식인 `number`, `string`, `Boolean` 및 `node set` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-112">The data types returned from extension objects are one of the four basic XPath data types of `number`, `string`, `Boolean`, and `node set`.</span></span>  
  
 <span data-ttu-id="e7eda-113">전달할 매개 변수 수를 지정하지 않아도 되는 `params` 키워드로 정의한 메서드는 현재 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-113">Any method that is defined with the `params` keyword, which allows an unspecified number of parameters to be passed, is not currently supported by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="e7eda-114">그러므로 `params` 키워드로 정의한 메서드를 사용하는 XSLT 스타일시트는 제대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-114">XSLT style sheets that utilize any method defined with the `params` keyword will not work correctly.</span></span> <span data-ttu-id="e7eda-115">자세한 내용은 참조 [params](~/docs/csharp/language-reference/keywords/params.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-115">For details, see [params](~/docs/csharp/language-reference/keywords/params.md).</span></span>  
  
### <a name="to-use-an-xslt-extension-object"></a><span data-ttu-id="e7eda-116">XSLT 확장명 개체를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="e7eda-116">To use an XSLT extension object</span></span>  
  
1.  <span data-ttu-id="e7eda-117"><xref:System.Xml.Xsl.XsltArgumentList> 개체를 만들고 <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> 메서드를 사용하여 확장 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-117">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span>  
  
2.  <span data-ttu-id="e7eda-118">스타일시트에서 확장 개체를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-118">Call the extension object from the style sheet.</span></span>  
  
3.  <span data-ttu-id="e7eda-119"><xref:System.Xml.Xsl.XsltArgumentList> 개체를 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e7eda-119">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7eda-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7eda-120">See Also</span></span>  
 [<span data-ttu-id="e7eda-121">XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="e7eda-121">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)  
 [<span data-ttu-id="e7eda-122">XSLT 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="e7eda-122">XSLT Security Considerations</span></span>](../../../../docs/standard/data/xml/xslt-security-considerations.md)

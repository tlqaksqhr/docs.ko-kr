---
title: "사용자 정의 함수 및 변수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 4772f20e-1e7f-496e-93c2-1484473be555
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b6870861541a063c56f83dcb286d21a5a970d1b1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="user-defined-functions-and-variables"></a><span data-ttu-id="6bafc-102">사용자 정의 함수 및 변수</span><span class="sxs-lookup"><span data-stu-id="6bafc-102">User Defined Functions and Variables</span></span>
<span data-ttu-id="6bafc-103"><xref:System.Xml.XPath.XPathNavigator> 클래스는 <xref:System.Xml.XPath.XPathDocument> 데이터와 상호 작용하는 데 사용되는 메서드 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods that are used to interact with <xref:System.Xml.XPath.XPathDocument> data.</span></span> <span data-ttu-id="6bafc-104">XPath 쿼리 식에서 사용되는 확장명 함수 및 변수를 구현하여 표준 XPath 함수를 보완할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-104">You can supplement the standard XPath functions by implementing extension functions and variables for use by XPath query expressions.</span></span> <span data-ttu-id="6bafc-105"><xref:System.Xml.XPath.XPathExpression.SetContext%2A> 메서드는 <xref:System.Xml.Xsl.XsltContext>에서 파생되는 사용자 정의 컨텍스트를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-105">The <xref:System.Xml.XPath.XPathExpression.SetContext%2A> method can accept a user defined context derived from <xref:System.Xml.Xsl.XsltContext>.</span></span> <span data-ttu-id="6bafc-106">사용자 정의 함수는 사용자 지정 컨텍스트로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-106">User defined functions are resolved by the custom context.</span></span>  
  
 <span data-ttu-id="6bafc-107">확장명 함수 및 변수는 XML 삽입 공격을 방지하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-107">Extension functions and variables can be useful in prevention of XML injection attacks.</span></span> <span data-ttu-id="6bafc-108">이러한 시나리오에서 사용자 입력은 처리 명령과 연결된 원시 입력이 아닌 사용자 지정 변수로 할당되고 확장명 함수로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-108">In these scenarios user input is assigned to custom variables and processed by extension functions, not as raw input concatenated with processing instructions.</span></span> <span data-ttu-id="6bafc-109">확장 함수 및 변수에는 사용자 입력이 포함되어 있어서 디자이너에서 의도한 대로 XML 데이터에 대해서만 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-109">Extension functions and variables contain user input so that it only acts on XML data as intended by the designer.</span></span>  
  
 <span data-ttu-id="6bafc-110">확장을 사용하려면 확장 함수 및 변수를 지원하는 인터페이스 <xref:System.Xml.Xsl.XsltContext> 및 <xref:System.Xml.Xsl.IXsltContextFunction>과 함께 사용자 지정 <xref:System.Xml.Xsl.IXsltContextVariable> 클래스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-110">To use extensions you implement a custom <xref:System.Xml.Xsl.XsltContext> class along with the interfaces <xref:System.Xml.Xsl.IXsltContextFunction> and <xref:System.Xml.Xsl.IXsltContextVariable> that support extension functions and variables.</span></span> <span data-ttu-id="6bafc-111"><xref:System.Xml.XPath.XPathExpression>은 사용자 입력을 <xref:System.Xml.Xsl.XsltArgumentList>와 함께 사용자 지정 <xref:System.Xml.Xsl.XsltContext>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-111">An <xref:System.Xml.XPath.XPathExpression> adds user input with its <xref:System.Xml.Xsl.XsltArgumentList> to the custom <xref:System.Xml.Xsl.XsltContext>.</span></span>  
  
 <span data-ttu-id="6bafc-112"><xref:System.Xml.XPath.XPathExpression>은 <xref:System.Xml.XPath.XPathNavigator>가 식에서 식별된 노드를 검색 및 처리하는 데 사용하는 컴파일된 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-112">The <xref:System.Xml.XPath.XPathExpression> represents a compiled query that <xref:System.Xml.XPath.XPathNavigator> uses to find and process the nodes identified by the expression.</span></span>  
  
 <span data-ttu-id="6bafc-113">다음 예제는 <xref:System.Xml.Xsl.XsltContext>에서 파생되는 사용자 지정 컨텍스트 클래스의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-113">The following example shows implementation of a custom context class derived from <xref:System.Xml.Xsl.XsltContext>.</span></span> <span data-ttu-id="6bafc-114">코드의 주석은 클래스 멤버 및 사용자 지정 함수에서의 클래스 멤버 사용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-114">Comments in the code describe class members and their use in custom functions.</span></span> <span data-ttu-id="6bafc-115">함수 및 변수 구현과 이러한 구현을 사용하는 샘플 응용 프로그램은 이 코드 세그먼트를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-115">Function and variable implementations and a sample application that uses these implementations follow this code segment.</span></span>  
  
 [!code-csharp[XPathExtensionFunctions#2](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#2)]
 [!code-vb[XPathExtensionFunctions#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#2)]  
  
 <span data-ttu-id="6bafc-116">다음 코드는 <xref:System.Xml.Xsl.IXsltContextFunction>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-116">The following code implements <xref:System.Xml.Xsl.IXsltContextFunction>.</span></span> <span data-ttu-id="6bafc-117"><xref:System.Xml.Xsl.IXsltContextFunction>을 구현하는 클래스는 사용자 정의 함수를 확인 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-117">The class that implements <xref:System.Xml.Xsl.IXsltContextFunction> resolves and executes user-defined functions.</span></span> <span data-ttu-id="6bafc-118">이 예제는 `private int CountChar(string title, char charTocount)` 선언에서 식별된 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-118">This example uses the function identified by the declaration: `private int CountChar(string title, char charTocount)`.</span></span>  
  
 <span data-ttu-id="6bafc-119">코드 주석은 클래스 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-119">Code comments describe class members.</span></span>  
  
 [!code-csharp[XPathExtensionFunctions#3](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#3)]
 [!code-vb[XPathExtensionFunctions#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#3)]  
  
 <span data-ttu-id="6bafc-120">다음 코드는 <xref:System.Xml.Xsl.IXsltContextVariable>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-120">The following code implements <xref:System.Xml.Xsl.IXsltContextVariable>.</span></span> <span data-ttu-id="6bafc-121">이 클래스는 XPath 쿼리 식의 사용자 정의 변수에 대한 참조를 런타임에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-121">This class resolves references to user-defined variables in XPath query expressions at run time.</span></span> <span data-ttu-id="6bafc-122">이 클래스의 인스턴스는 사용자 지정 <xref:System.Xml.Xsl.XsltContext.ResolveVariable%2A> 클래스의 재정의된 <xref:System.Xml.Xsl.XsltContext> 메서드에서 생성 및 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-122">An instance of this class is created and returned by the overridden <xref:System.Xml.Xsl.XsltContext.ResolveVariable%2A> method of the custom <xref:System.Xml.Xsl.XsltContext> class.</span></span>  
  
 <span data-ttu-id="6bafc-123">코드 주석은 클래스 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-123">Code comments describe the class members.</span></span>  
  
 [!code-csharp[XPathExtensionFunctions#4](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#4)]
 [!code-vb[XPathExtensionFunctions#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#4)]  
  
 <span data-ttu-id="6bafc-124">다음 코드는 범위에 있는 이전 클래스 정의를 통해 사용자 지정 함수를 사용하여 `Tasks.xml` 문서의 요소에서 문자 수를 카운트합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-124">With the previous class definitions in scope, the following code uses the custom function to count characters in the elements of the `Tasks.xml` document.</span></span> <span data-ttu-id="6bafc-125">코드의 주석은 사용자 지정 함수를 컴파일하고 `Tasks.xml` 문서에 대해 이를 실행하는 코드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-125">Comments in the code describe the code that compiles the custom function and runs it against the `Tasks.xml` document.</span></span>  
  
 [!code-csharp[XPathExtensionFunctions#1](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#1)]
 [!code-vb[XPathExtensionFunctions#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#1)]  
  
 <span data-ttu-id="6bafc-126">이 예제에서는 다음 XML 데이터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6bafc-126">This example uses the following XML data.</span></span>  
  
 [!code-xml[XPathExtensionFunctions#5](../../../../samples/snippets/xml/VS_Snippets_Data/xpathextensionfunctions/XML/tasks.xml#5)]

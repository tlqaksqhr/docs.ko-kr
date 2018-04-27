---
title: System.Xml 사용법
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7e90dea873a007c9f148228a2566ff22d91185a3
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="systemxml-usage"></a><span data-ttu-id="b3ba6-102">System.Xml 사용법</span><span class="sxs-lookup"><span data-stu-id="b3ba6-102">System.Xml Usage</span></span>
<span data-ttu-id="b3ba6-103">이 섹션에 있는 여러 유형의 사용에 대 한 설명 <xref:System.Xml?displayProperty=nameWithType> XML 데이터를 나타내기 위해 사용할 수 있는 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b3ba6-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>  
  
 <span data-ttu-id="b3ba6-104">**X 하지 않으면** 사용 <xref:System.Xml.XmlNode> 또는 <xref:System.Xml.XmlDocument> XML 데이터를 표시 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3ba6-104">**X DO NOT** use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="b3ba6-105">인스턴스를 사용 하 여 유사한 <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, 또는 유형의 하위 <xref:System.Xml.Linq.XNode> 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3ba6-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="b3ba6-106">`XmlNode` 및 `XmlDocument` 공용 Api에서 노출 하는 데 설계 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3ba6-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>  
  
 <span data-ttu-id="b3ba6-107">**✓ 않습니다** 사용 `XmlReader`, `IXPathNavigable`, 또는 유형의 하위 `XNode` 입력 또는 출력을 사용 하거나 XML을 반환 하는 멤버의으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3ba6-107">**✓ DO** use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>  
  
 <span data-ttu-id="b3ba6-108">대신 이러한 추상화를 사용 하 여 `XmlDocument`, `XmlNode`, 또는 <xref:System.Xml.XPath.XPathDocument>없기 때문에이 분리 하는 메모리 내 XML 문서의 특정 구현에서 메서드를 노출 하는 가상 XML 데이터 원본으로 작업 하도록 허용 `XNode` `XmlReader`, 또는 <xref:System.Xml.XPath.XPathNavigator>합니다.</span><span class="sxs-lookup"><span data-stu-id="b3ba6-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="b3ba6-109">**X 하지 않으면** 하위 클래스 `XmlDocument` 경우 만들려면 기본 개체 모델 또는 데이터 원본에 대 한 XML 뷰를 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b3ba6-109">**X DO NOT** subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>  
  
 <span data-ttu-id="b3ba6-110">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="b3ba6-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b3ba6-111">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="b3ba6-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ba6-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3ba6-112">See Also</span></span>  
 [<span data-ttu-id="b3ba6-113">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b3ba6-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="b3ba6-114">사용 지침</span><span class="sxs-lookup"><span data-stu-id="b3ba6-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)

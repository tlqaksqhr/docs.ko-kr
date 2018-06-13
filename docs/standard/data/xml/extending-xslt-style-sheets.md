---
title: XSLT 스타일시트 확장
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: df4ba2bf-a99e-4d22-bbf3-04fc67669dbc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff952df59dc8291b12df2b238052d4c40c834e2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568825"
---
# <a name="extending-xslt-style-sheets"></a><span data-ttu-id="738e3-102">XSLT 스타일시트 확장</span><span class="sxs-lookup"><span data-stu-id="738e3-102">Extending XSLT Style Sheets</span></span>
<span data-ttu-id="738e3-103">이 단원에서는 XSLT 기능을 확장하는 여러 가지 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="738e3-103">This section describes the different methods of extending the XSLT functionality.</span></span> <span data-ttu-id="738e3-104"><xref:System.Xml.Xsl.XsltArgumentList> 클래스를 사용하여 확장 개체 또는 매개 변수를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="738e3-104">You can add extension objects or parameters using the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span> <span data-ttu-id="738e3-105">그런 다음 스타일시트에서 확장명 개체 및 매개 변수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="738e3-105">The extension objects or parameters can then be called from the style sheet.</span></span> <span data-ttu-id="738e3-106">또한 `msxsl:script` 요소를 사용하여 스크립트 블록을 스타일시트에 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="738e3-106">In addition, you can also embed script blocks into the style sheet by using the `msxsl:script` element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="738e3-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="738e3-107">In This Section</span></span>  
 [<span data-ttu-id="738e3-108">XSLT 확장명 개체</span><span class="sxs-lookup"><span data-stu-id="738e3-108">XSLT Extension Objects</span></span>](../../../../docs/standard/data/xml/xslt-extension-objects.md)  
 <span data-ttu-id="738e3-109"><xref:System.Xml.Xsl.XsltArgumentList> 클래스를 사용하여 XSLT 확장 개체를 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="738e3-109">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT extension objects.</span></span>  
  
 [<span data-ttu-id="738e3-110">XSLT 매개 변수</span><span class="sxs-lookup"><span data-stu-id="738e3-110">XSLT Parameters</span></span>](../../../../docs/standard/data/xml/xslt-parameters.md)  
 <span data-ttu-id="738e3-111"><xref:System.Xml.Xsl.XsltArgumentList> 클래스를 사용하여 XSLT 매개 변수를 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="738e3-111">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT parameters.</span></span>  
  
 [<span data-ttu-id="738e3-112">msxsl:script를 사용하는 스크립트 블록</span><span class="sxs-lookup"><span data-stu-id="738e3-112">Script Blocks Using msxsl:script</span></span>](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md)  
 <span data-ttu-id="738e3-113">`msxsl:script` 요소를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="738e3-113">Discusses using the `msxsl:script` element.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="738e3-114">관련 단원</span><span class="sxs-lookup"><span data-stu-id="738e3-114">Related Sections</span></span>  
 [<span data-ttu-id="738e3-115">XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="738e3-115">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)

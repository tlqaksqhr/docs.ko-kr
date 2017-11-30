---
title: "XSLT 스타일시트 확장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df4ba2bf-a99e-4d22-bbf3-04fc67669dbc
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8ccd1a95586bc92bcc712639eded135a69da1a36
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="extending-xslt-style-sheets"></a><span data-ttu-id="e0800-102">XSLT 스타일시트 확장</span><span class="sxs-lookup"><span data-stu-id="e0800-102">Extending XSLT Style Sheets</span></span>
<span data-ttu-id="e0800-103">이 단원에서는 XSLT 기능을 확장하는 여러 가지 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0800-103">This section describes the different methods of extending the XSLT functionality.</span></span> <span data-ttu-id="e0800-104"><xref:System.Xml.Xsl.XsltArgumentList> 클래스를 사용하여 확장 개체 또는 매개 변수를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0800-104">You can add extension objects or parameters using the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span> <span data-ttu-id="e0800-105">그런 다음 스타일시트에서 확장 개체 및 매개 변수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0800-105">The extension objects or parameters can then be called from the style sheet.</span></span> <span data-ttu-id="e0800-106">또한 `msxsl:script` 요소를 사용하여 스크립트 블록을 스타일시트에 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0800-106">In addition, you can also embed script blocks into the style sheet by using the `msxsl:script` element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0800-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="e0800-107">In This Section</span></span>  
 [<span data-ttu-id="e0800-108">XSLT 확장명 개체</span><span class="sxs-lookup"><span data-stu-id="e0800-108">XSLT Extension Objects</span></span>](../../../../docs/standard/data/xml/xslt-extension-objects.md)  
 <span data-ttu-id="e0800-109"><xref:System.Xml.Xsl.XsltArgumentList> 클래스를 사용하여 XSLT 확장 개체를 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0800-109">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT extension objects.</span></span>  
  
 [<span data-ttu-id="e0800-110">XSLT 매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0800-110">XSLT Parameters</span></span>](../../../../docs/standard/data/xml/xslt-parameters.md)  
 <span data-ttu-id="e0800-111"><xref:System.Xml.Xsl.XsltArgumentList> 클래스를 사용하여 XSLT 매개 변수를 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0800-111">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT parameters.</span></span>  
  
 [<span data-ttu-id="e0800-112">스크립트 블록에서 사용 하 여 msxsl: script</span><span class="sxs-lookup"><span data-stu-id="e0800-112">Script Blocks Using msxsl:script</span></span>](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md)  
 <span data-ttu-id="e0800-113">`msxsl:script` 요소를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0800-113">Discusses using the `msxsl:script` element.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e0800-114">관련 단원</span><span class="sxs-lookup"><span data-stu-id="e0800-114">Related Sections</span></span>  
 [<span data-ttu-id="e0800-115">XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="e0800-115">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)

---
title: "방법: FlowDocument 열 구분 속성 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7e4a300acccd0c6915844c988a4bbc81426f90f0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a><span data-ttu-id="cb593-102">방법: FlowDocument 열 구분 속성 사용</span><span class="sxs-lookup"><span data-stu-id="cb593-102">How to: Use FlowDocument Column-Separating Attributes</span></span>
<span data-ttu-id="cb593-103">열 구분 기능을 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Documents.FlowDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="cb593-103">This example shows how to use the column-separating features of a <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb593-104">예제</span><span class="sxs-lookup"><span data-stu-id="cb593-104">Example</span></span>  
 <span data-ttu-id="cb593-105">다음 예제에서는 정의 <xref:System.Windows.Documents.FlowDocument>, 설정 및는 <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, 및 <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="cb593-105">The following example defines a <xref:System.Windows.Documents.FlowDocument>, and sets the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes.</span></span>  <span data-ttu-id="cb593-106"><xref:System.Windows.Documents.FlowDocument> 단일 단락 샘플 콘텐츠를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb593-106">The <xref:System.Windows.Documents.FlowDocument> contains a single paragraph of sample content.</span></span>  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 <span data-ttu-id="cb593-107">다음 그림은의 효과 <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, 및 <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> 렌더링 된 특성 <xref:System.Windows.Documents.FlowDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="cb593-107">The following figure shows the effects of the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes in a rendered <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="cb593-108">![스크린 샷: FlowDocument 내부 열](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span><span class="sxs-lookup"><span data-stu-id="cb593-108">![Screenshot: FlowDocument Intra Column](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span></span>

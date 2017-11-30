---
title: "방법: GruopBox 템플릿 정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7b6312575dbf44b7c4ae872fbb87df41eb2e32ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-groupbox-template"></a><span data-ttu-id="12aec-102">방법: GruopBox 템플릿 정의</span><span class="sxs-lookup"><span data-stu-id="12aec-102">How to: Define a GroupBox Template</span></span>
<span data-ttu-id="12aec-103">에 대 한 템플릿을 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="12aec-103">This example shows how to create a template for a <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12aec-104">예제</span><span class="sxs-lookup"><span data-stu-id="12aec-104">Example</span></span>  
 <span data-ttu-id="12aec-105">다음 예제에서는 정의 <xref:System.Windows.Controls.GroupBox> 컨트롤 템플릿을 사용 하 여 한 <xref:System.Windows.Controls.Grid> 레이아웃에 대 한 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="12aec-105">The following example defines a <xref:System.Windows.Controls.GroupBox> control template by using a <xref:System.Windows.Controls.Grid> control for layout.</span></span> <span data-ttu-id="12aec-106">템플릿을 사용 하 여 한 <xref:System.Windows.Controls.BorderGapMaskConverter> 의 테두리를 정의 하는 <xref:System.Windows.Controls.GroupBox> 테두리를 가리지 않습니다 있도록는 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="12aec-106">The template uses a <xref:System.Windows.Controls.BorderGapMaskConverter> to define the border of the <xref:System.Windows.Controls.GroupBox> so that the border does not obscure the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> content.</span></span>  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a><span data-ttu-id="12aec-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12aec-107">See Also</span></span>  
 <xref:System.Windows.Controls.GroupBox>  
 [<span data-ttu-id="12aec-108">GroupBox 방법 도움말 항목</span><span class="sxs-lookup"><span data-stu-id="12aec-108">GroupBox How-to Topics</span></span>](http://msdn.microsoft.com/en-us/7692e155-a4c6-428c-b7e0-64b3740daca7)

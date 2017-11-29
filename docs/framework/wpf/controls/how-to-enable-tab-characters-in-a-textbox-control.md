---
title: "방법: TextBox 컨트롤에서 탭 문자 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TextBox control [WPF], enabling tab characters
- tab characters [WPF], enabling
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc77668d9544cb37a8c9d1fcbdc3ed0351bc9eef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-tab-characters-in-a-textbox-control"></a><span data-ttu-id="4b662-102">방법: TextBox 컨트롤에서 탭 문자 사용</span><span class="sxs-lookup"><span data-stu-id="4b662-102">How to: Enable Tab Characters in a TextBox Control</span></span>
<span data-ttu-id="4b662-103">탭 문자에 대 한 동의에서 일반 입력으로 사용 하도록 설정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b662-103">This example shows how to enable the acceptance of tab characters as normal input in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b662-104">예제</span><span class="sxs-lookup"><span data-stu-id="4b662-104">Example</span></span>  
 <span data-ttu-id="4b662-105">입력으로 수락이 탭 문자를 사용 하도록 설정 하려면 한 <xref:System.Windows.Controls.TextBox> 제어, 설정는 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> 특성을 **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="4b662-105">To enable the acceptance of tab characters as input in a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_EnablingTab#_AcceptsTab](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## <a name="see-also"></a><span data-ttu-id="4b662-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b662-106">See Also</span></span>  
 [<span data-ttu-id="4b662-107">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="4b662-107">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="4b662-108">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="4b662-108">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)

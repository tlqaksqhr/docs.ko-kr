---
title: "방법: TextBox에 워터마크 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92d619cb713e22d49e5c62bf7545d946b418dbda
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="d6490-102">방법: TextBox에 워터마크 추가</span><span class="sxs-lookup"><span data-stu-id="d6490-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="d6490-103">다음 예제에서는의 유용성는 <xref:System.Windows.Controls.TextBox> 내부의 설명 배경 이미지를 표시 하 여는 <xref:System.Windows.Controls.TextBox> 이미지 제거 되는 지점에 사용자가 텍스트를 입력 될 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6490-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="d6490-104">또한 사용자가 입력 내용을 제거 하는 경우 배경 이미지가 다시 복원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6490-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="d6490-105">아래 그림을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6490-105">See illustration below.</span></span>  
  
 <span data-ttu-id="d6490-106">![배경 이미지가 있는 TextBox](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="d6490-106">![A TextBox with a background image](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6490-107">대신 다음 단순히 조작이 예제에는 배경 이미지를 사용 하는 이유는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성 <xref:System.Windows.Controls.TextBox>은 데이터 바인딩을 사용할 배경 이미지를 방해 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6490-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6490-108">예</span><span class="sxs-lookup"><span data-stu-id="d6490-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d6490-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6490-109">See Also</span></span>  
 [<span data-ttu-id="d6490-110">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="d6490-110">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="d6490-111">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="d6490-111">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)

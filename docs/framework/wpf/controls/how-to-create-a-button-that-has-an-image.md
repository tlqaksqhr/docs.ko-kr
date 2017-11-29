---
title: "방법: 이미지가 있는 단추 만들기"
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
helpviewer_keywords: Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa3aa5454629d53fd8864df6a4f204e22028208f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="57597-102">방법: 이미지가 있는 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="57597-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="57597-103">에 이미지를 포함 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="57597-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57597-104">예제</span><span class="sxs-lookup"><span data-stu-id="57597-104">Example</span></span>  
 <span data-ttu-id="57597-105">다음 예제에서는 두 개의 <xref:System.Windows.Controls.Button> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="57597-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="57597-106">하나의 <xref:System.Windows.Controls.Button> 텍스트가 포함 된 이미지를 포함 하는 다른 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="57597-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="57597-107">이미지는 데이터를 예에 나오는 프로젝트 폴더의 하위 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="57597-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="57597-108">사용자가 클릭할 때는 <xref:System.Windows.Controls.Button> 이미지, 백그라운드 및 다른 텍스트 있는 <xref:System.Windows.Controls.Button> 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="57597-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="57597-109">이 예에서는 만듭니다 <xref:System.Windows.Controls.Button> 태그를 사용 하 여 제어 하지만 코드를 사용 하 여 작성 하는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="57597-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="57597-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57597-110">See Also</span></span>  
 [<span data-ttu-id="57597-111">컨트롤</span><span class="sxs-lookup"><span data-stu-id="57597-111">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
 [<span data-ttu-id="57597-112">컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="57597-112">Control Library</span></span>](../../../../docs/framework/wpf/controls/control-library.md)

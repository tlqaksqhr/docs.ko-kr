---
title: "방법: 이미지가 있는 단추 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e95f027a8e3568365fa7957c36241b6ec2c30d28
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="7af83-102">방법: 이미지가 있는 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="7af83-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="7af83-103">에 이미지를 포함 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="7af83-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7af83-104">예</span><span class="sxs-lookup"><span data-stu-id="7af83-104">Example</span></span>  
 <span data-ttu-id="7af83-105">다음 예제에서는 두 개의 <xref:System.Windows.Controls.Button> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="7af83-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="7af83-106">하나의 <xref:System.Windows.Controls.Button> 텍스트가 포함 된 이미지를 포함 하는 다른 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="7af83-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="7af83-107">이미지는 데이터를 예에 나오는 프로젝트 폴더의 하위 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="7af83-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="7af83-108">사용자가 클릭할 때는 <xref:System.Windows.Controls.Button> 이미지, 백그라운드 및 다른 텍스트 있는 <xref:System.Windows.Controls.Button> 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="7af83-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="7af83-109">이 예에서는 만듭니다 <xref:System.Windows.Controls.Button> 태그를 사용 하 여 제어 하지만 코드를 사용 하 여 작성 하는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="7af83-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="7af83-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7af83-110">See Also</span></span>  
 [<span data-ttu-id="7af83-111">컨트롤</span><span class="sxs-lookup"><span data-stu-id="7af83-111">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
 [<span data-ttu-id="7af83-112">컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="7af83-112">Control Library</span></span>](../../../../docs/framework/wpf/controls/control-library.md)

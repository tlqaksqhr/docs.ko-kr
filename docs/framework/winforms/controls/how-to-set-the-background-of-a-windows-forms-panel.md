---
title: '방법: Windows Forms 패널의 배경 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: ff0c748cfb7b38c41b2ede211aed7bf6e6f68544
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534789"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a><span data-ttu-id="675e5-102">방법: Windows Forms 패널의 배경 설정</span><span class="sxs-lookup"><span data-stu-id="675e5-102">How to: Set the Background of a Windows Forms Panel</span></span>
<span data-ttu-id="675e5-103">Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤 배경 색과 배경 이미지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="675e5-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="675e5-104"><xref:System.Windows.Forms.Control.BackColor%2A> 속성 라디오 단추 레이블 등 포함된 된 컨트롤에 대 한 배경색을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="675e5-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for the contained controls, such as labels and radio buttons.</span></span> <span data-ttu-id="675e5-105">경우는 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 되어 있지는 <xref:System.Windows.Forms.Control.BackColor%2A> 선택에서 전체 패널을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="675e5-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill the entire panel.</span></span> <span data-ttu-id="675e5-106">경우는 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정 되어 있으면 포함 된 컨트롤 뒤 이미지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="675e5-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the contained controls.</span></span>  
  
### <a name="to-set-the-background-programmatically"></a><span data-ttu-id="675e5-107">배경을 프로그래밍 방식으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="675e5-107">To set the background programmatically</span></span>  
  
1.  <span data-ttu-id="675e5-108">패널의 설정 <xref:System.Windows.Forms.Control.BackColor%2A> 속성 형식의 값을 <xref:System.Drawing.Color?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="675e5-108">Set the panel's <xref:System.Windows.Forms.Control.BackColor%2A> property to a value of type <xref:System.Drawing.Color?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2.  <span data-ttu-id="675e5-109">패널의 설정 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 사용 하 여 속성의 <xref:System.Drawing.Image.FromFile%2A> 의 메서드는 <xref:System.Drawing.Image?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="675e5-109">Set the panel's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image?displayProperty=nameWithType> class.</span></span>  
  
    ```vb  
    ' You should replace the bolded image   
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="675e5-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="675e5-110">See Also</span></span>  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [<span data-ttu-id="675e5-111">Panel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="675e5-111">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [<span data-ttu-id="675e5-112">Panel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="675e5-112">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)

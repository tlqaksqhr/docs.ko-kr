---
title: '방법: 컨트롤에 투명한 배경 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: ad814c9179fd33955fe4df2666f8a47606bfbff0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531819"
---
# <a name="how-to-give-your-control-a-transparent-background"></a><span data-ttu-id="0f7af-102">방법: 컨트롤에 투명한 배경 적용</span><span class="sxs-lookup"><span data-stu-id="0f7af-102">How to: Give Your Control a Transparent Background</span></span>
<span data-ttu-id="0f7af-103">.NET Framework의 이전 버전에서는 양식 생성자에 먼저 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 설정하지 않으면 컨트롤이 투명 배경색 설정을 지원하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7af-103">In earlier versions of the .NET Framework, controls didn't support setting transparent backcolors without first setting the <xref:System.Windows.Forms.Control.SetStyle%2A> method in the forms's constructor.</span></span> <span data-ttu-id="0f7af-104">현재 프레임워크 버전에서는 대부분의 컨트롤에 대한 배경색을 디자인 타임에 <xref:System.Drawing.Color.Transparent%2A> 속성 **창 또는 양식 생성자의 코드에서** 으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7af-104">In the current framework version, the backcolor for most controls can be set to <xref:System.Drawing.Color.Transparent%2A> in the **Properties** window at design time, or in code in the form's constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f7af-105">Windows Forms 컨트롤은 진정한 투명성을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7af-105">Windows Forms controls do not support true transparency.</span></span> <span data-ttu-id="0f7af-106">투명한 Windows Forms 컨트롤의 배경은 해당 부모가 색칠합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7af-106">The background of a transparent Windows Forms control is painted by its parent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f7af-107"><xref:System.Windows.Controls.Button> 속성이 <xref:System.Windows.Forms.ButtonBase.BackColor%2A> 으로 설정된 경우에도 <xref:System.Drawing.Color.Transparent%2A>컨트롤은 투명한 배경색을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f7af-107">The <xref:System.Windows.Controls.Button> control doesn't support a transparent backcolor even when the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property is set to <xref:System.Drawing.Color.Transparent%2A>.</span></span>  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a><span data-ttu-id="0f7af-108">컨트롤에 투명한 배경색을 적용하려면</span><span class="sxs-lookup"><span data-stu-id="0f7af-108">To give your control a transparent backcolor</span></span>  
  
-   <span data-ttu-id="0f7af-109">속성 창에서 <xref:System.Windows.Forms.ButtonBase.BackColor%2A> 속성을 선택하고 <xref:System.Drawing.Color.Transparent%2A>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f7af-109">In the Properties window, choose the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property and set it to <xref:System.Drawing.Color.Transparent%2A></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f7af-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f7af-110">See Also</span></span>  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [<span data-ttu-id="0f7af-111">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="0f7af-111">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="0f7af-112">관리되는 그래픽 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="0f7af-112">Using Managed Graphics Classes</span></span>](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 [<span data-ttu-id="0f7af-113">방법: 불투명 및 반투명 선 그리기</span><span class="sxs-lookup"><span data-stu-id="0f7af-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)

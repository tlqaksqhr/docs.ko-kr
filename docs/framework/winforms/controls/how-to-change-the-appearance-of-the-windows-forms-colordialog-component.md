---
title: "방법: Windows Forms ColorDialog 구성 요소의 모양 변경"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 11edb1019b8fedde368d712ab27dd0954a2de50a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="55cd3-102">방법: Windows Forms ColorDialog 구성 요소의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="55cd3-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="55cd3-103">Windows Forms의 모양을 구성할 수 있습니다 <xref:System.Windows.Forms.ColorDialog> 다양 한 속성이 해당 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="55cd3-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="55cd3-104">대화 상자에 다음 두 섹션이-기본 색을 사용자 지정 색을 정의할 수 있도록 표시 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="55cd3-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="55cd3-105">대부분의 속성 대화 상자에서 선택할 수 있는 색을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="55cd3-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="55cd3-106">경우는 <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> 속성이로 설정 되어 `true`, 사용자가 사용자 지정 색을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55cd3-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="55cd3-107"><xref:System.Windows.Forms.ColorDialog.FullOpen%2A> 속성은 `true` ; 사용자 지정 색을 정의 하 여 대화 상자 확장 되 면 그렇지 않은 경우 사용자를 클릭 해야 "사용자 지정 색 만들기" 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="55cd3-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="55cd3-108">경우는 <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> 속성이로 설정 되어 `true`, 대화 상자 기본 색 집합에서 사용 가능한 모든 색을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="55cd3-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="55cd3-109">경우는 <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 속성이 `true`, 사용자 디더링된 색을 선택할 수 없으므로 단색만 선택할 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55cd3-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="55cd3-110">경우는 <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 속성이 `true`, 대화 상자에 도움말 단추가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="55cd3-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="55cd3-111">사용자가 도움말 단추를 클릭 하면는 <xref:System.Windows.Forms.ColorDialog> 구성 요소의 <xref:System.Windows.Forms.CommonDialog.HelpRequest> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="55cd3-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="55cd3-112">색 대화 상자의 모양을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="55cd3-112">To configure the appearance of the color dialog box</span></span>  
  
1.  <span data-ttu-id="55cd3-113">설정의 <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, 및 <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 속성을 원하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="55cd3-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="55cd3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55cd3-114">See Also</span></span>  
 <xref:System.Windows.Forms.ColorDialog>  
 [<span data-ttu-id="55cd3-115">ColorDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="55cd3-115">ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [<span data-ttu-id="55cd3-116">ColorDialog 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="55cd3-116">ColorDialog Component Overview</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)

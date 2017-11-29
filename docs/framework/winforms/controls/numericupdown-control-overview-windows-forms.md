---
title: "NumericUpDown 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e1afb128fd5e098a59fa2636f09998a2a463c926
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="numericupdown-control-overview-windows-forms"></a><span data-ttu-id="e7ff7-102">NumericUpDown 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e7ff7-102">NumericUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="e7ff7-103"><xref:System.Windows.Forms.NumericUpDown> 제어는 텍스트 상자가 조합과 한 쌍의 값을 조정 하기 위해 클릭할 수 화살표가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-103">The <xref:System.Windows.Forms.NumericUpDown> control looks like a combination of a text box and a pair of arrows that the user can click to adjust a value.</span></span> <span data-ttu-id="e7ff7-104">컨트롤은 표시 하거나 고정 된 숫자 값 선택 목록에서 단일 숫자 값을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-104">The control displays and sets a single numeric value from a list of fixed numeric-value choices.</span></span> <span data-ttu-id="e7ff7-105">사용자를 늘리고 컨트롤의 텍스트 상자 부분에 숫자를 입력 하거나 위쪽 및 아래쪽 화살표 키를 누르거나 및 아래쪽 화살표를 위쪽을 클릭 하 여 수를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-105">The user can increase and decrease the number by clicking the up and down arrows, by pressing the UP and DOWN ARROW keys, or by typing a number in the text box part of the control.</span></span> <span data-ttu-id="e7ff7-106">최대; 방향으로 번호를 이동 위쪽 화살표 키를 클릭 하면 아래쪽 화살표 키를 클릭 하면 최소값으로 수 만큼 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-106">Clicking the UP ARROW key moves the number toward the maximum; clicking the DOWN ARROW key moves the number toward the minimum.</span></span>  
  
 <span data-ttu-id="e7ff7-107">여러 유용한 기능이이 컨트롤 이므로 가장 적합 한 클래스, 예를 들어 음악 플레이어 응용 프로그램에 대 한 볼륨 컨트롤을 만들려는 경우.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-107">Because of its versatile functionality, this control is an obvious choice, for example, if you want to create a volume control for a music player application.</span></span> <span data-ttu-id="e7ff7-108"><xref:System.Windows.Forms.NumericUpDown> 많은 Windows 제어판 응용 프로그램에서 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-108">The <xref:System.Windows.Forms.NumericUpDown> control is used in many Windows Control Panel applications.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="e7ff7-109">키 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="e7ff7-109">Key Properties and Methods</span></span>  
 <span data-ttu-id="e7ff7-110">컨트롤의 텍스트 상자에 표시 수 16 진수에 다양 한 형식으로 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-110">The numbers displayed in the control's text box can be in a variety of formats, including hexadecimal.</span></span> <span data-ttu-id="e7ff7-111">자세한 내용은 참조 [하는 방법: Windows Forms NumericUpDown 컨트롤의 형식을 설정](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-111">For more information, see [How to: Set the Format for the Windows Forms NumericUpDown Control](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md).</span></span> <span data-ttu-id="e7ff7-112">컨트롤의 주요 속성은 <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (기본값 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (기본값 0), 및 <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (기본값 1).</span><span class="sxs-lookup"><span data-stu-id="e7ff7-112">The key properties of the control are <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (default value 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (default value 0), and <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (default value 1).</span></span> <span data-ttu-id="e7ff7-113"><xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성 컨트롤에서 선택한 현재 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-113">The <xref:System.Windows.Forms.NumericUpDown.Value%2A> property sets the current number selected in the control.</span></span> <span data-ttu-id="e7ff7-114"><xref:System.Windows.Forms.NumericUpDown.Increment%2A> 속성 up를 클릭할 때 / 아래쪽 화살표 수 조정 되는 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-114">The <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property sets the amount that the number is adjusted by when the user clicks an up or down arrow.</span></span> <span data-ttu-id="e7ff7-115">포커스가 컨트롤 밖으로 이동, 입력 된 모든 최소 및 최대 숫자 값에 대해 유효성이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-115">When focus moves off the control, any typed input will be validated against the minimum and maximum numeric values.</span></span> <span data-ttu-id="e7ff7-116">지속적으로 누를 때 위쪽 또는 아래쪽 화살표를 컨트롤 번호를 통해 이동 하는 속도 높일 수와 <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-116">You can increase the speed that the control moves through numbers, when the user continuously presses the up or down arrow, with the <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> property.</span></span> <span data-ttu-id="e7ff7-117">컨트롤의 주요 메서드는 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> 및 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="e7ff7-117">The key methods of the control are <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7ff7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7ff7-118">See Also</span></span>  
 <xref:System.Windows.Forms.NumericUpDown>  
 [<span data-ttu-id="e7ff7-119">NumericUpDown 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e7ff7-119">NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [<span data-ttu-id="e7ff7-120">방법: Windows Forms NumericUpDown 컨트롤의 형식 설정</span><span class="sxs-lookup"><span data-stu-id="e7ff7-120">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)  
 [<span data-ttu-id="e7ff7-121">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e7ff7-121">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)

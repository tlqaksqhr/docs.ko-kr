---
title: "방법: 읽기 전용 텍스트 상자 만들기(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9cf6064442c3b648116f98f98f169dac12e5e88c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="e3f27-102">방법: 읽기 전용 텍스트 상자 만들기(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e3f27-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>
<span data-ttu-id="e3f27-103">읽기 전용 컨트롤에 있는 편집 가능한 Windows Forms의 텍스트 상자를 변형할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f27-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="e3f27-104">예를 들어 텍스트 상자는 일반적으로 편집 되지만 아닐 현재 응용 프로그램의 상태로 인해 하는 값을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f27-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>  
  
### <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="e3f27-105">읽기 전용 텍스트 상자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e3f27-105">To create a read-only text box</span></span>  
  
1.  <span data-ttu-id="e3f27-106">설정의 <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f27-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="e3f27-107">속성 설정 하 여 `true`, 사용자가 여전히 스크롤 및 변경을 허용 하지 않고 텍스트 상자에 텍스트를 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f27-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="e3f27-108">A **복사** 명령은 사용할 텍스트 상자에 있지만 **잘라내기** 및 **붙여넣기** 명령을 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f27-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e3f27-109"><xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 속성이 런타임 시 사용자 상호 작용에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3f27-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="e3f27-110">변경할 수 있습니다 여전히 텍스트 상자의 내용을 프로그래밍 방식으로 런타임에 변경 하 여는 <xref:System.Windows.Forms.TextBox.Text%2A> 입력란의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f27-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3f27-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3f27-111">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="e3f27-112">TextBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="e3f27-112">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="e3f27-113">방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어</span><span class="sxs-lookup"><span data-stu-id="e3f27-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="e3f27-114">방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기</span><span class="sxs-lookup"><span data-stu-id="e3f27-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="e3f27-115">방법: 문자열에 인용 부호 넣기</span><span class="sxs-lookup"><span data-stu-id="e3f27-115">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="e3f27-116">방법: Windows Forms TextBox 컨트롤에서 텍스트 선택</span><span class="sxs-lookup"><span data-stu-id="e3f27-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="e3f27-117">방법: Windows Forms TextBox 컨트롤에 여러 줄 표시</span><span class="sxs-lookup"><span data-stu-id="e3f27-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="e3f27-118">TextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e3f27-118">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)

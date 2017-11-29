---
title: "방법: ComboBox 컨트롤에서 가변 크기 텍스트 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
helpviewer_keywords:
- text [Windows Forms], drawing in combo boxes
- examples [Windows Forms], ComboBox control
- combo boxes [Windows Forms], drawing text
- ComboBox control [Windows Forms], examples [C#]
- ComboBox control [Windows Forms], drawing custom text
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a6f0dcfd24414ef868a1a5414af4fcde1b9a14ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a><span data-ttu-id="7c35e-102">방법: ComboBox 컨트롤에서 가변 크기 텍스트 만들기</span><span class="sxs-lookup"><span data-stu-id="7c35e-102">How to: Create Variable Sized Text in a ComboBox Control</span></span>
<span data-ttu-id="7c35e-103">이 예제에서는 텍스트에 대 한 사용자 지정 그리기를 <xref:System.Windows.Forms.ComboBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c35e-103">This example demonstrates custom drawing of text in a <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="7c35e-104">항목이 특정 조건에 부합 하는 경우 더 큰 글꼴로 그려집니다 이며 빨간색으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c35e-104">When an item meets a certain criteria, it is drawn in a larger font and turned red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c35e-105">예제</span><span class="sxs-lookup"><span data-stu-id="7c35e-105">Example</span></span>  
  
```vb  
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
    Dim siText As SizeF  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _  
lFont)  
    Else  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)  
    End If  
  
    e.ItemHeight = siText.Height  
    e.ItemWidth = siText.Width  
End Sub  
  
Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem  
    Dim g As Graphics = e.Graphics  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _  
e.Bounds.X, e.Bounds.Y)  
    Else  
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)  
    End If  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7c35e-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7c35e-106">Compiling the Code</span></span>  
 <span data-ttu-id="7c35e-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7c35e-107">This example requires:</span></span>  
  
-   <span data-ttu-id="7c35e-108">Windows form입니다.</span><span class="sxs-lookup"><span data-stu-id="7c35e-108">A Windows form.</span></span>  
  
-   <span data-ttu-id="7c35e-109">A <xref:System.Windows.Forms.ComboBox> 라는 컨트롤 `ListBox1` 의 세 가지 항목으로는 <xref:System.Windows.Forms.ComboBox.Items%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7c35e-109">A <xref:System.Windows.Forms.ComboBox> control named `ListBox1` with three items in the <xref:System.Windows.Forms.ComboBox.Items%2A> property.</span></span> <span data-ttu-id="7c35e-110">이 예제에서 세 가지 항목 이름은 `"One", Two", and Three"`합니다.</span><span class="sxs-lookup"><span data-stu-id="7c35e-110">In this example, the three items are named `"One", Two", and Three"`.</span></span> <span data-ttu-id="7c35e-111"><xref:System.Windows.Forms.ComboBox.DrawMode%2A> 속성 `ComboBox1` 로 설정 해야 <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>합니다.</span><span class="sxs-lookup"><span data-stu-id="7c35e-111">The <xref:System.Windows.Forms.ComboBox.DrawMode%2A> property of `ComboBox1` must be set to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7c35e-112">이 기술은에 적용 됩니다는 <xref:System.Windows.Forms.ListBox> 컨트롤-대신 사용할 수 있습니다는 <xref:System.Windows.Forms.ListBox> 에 대 한는 <xref:System.Windows.Forms.ComboBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="7c35e-112">This technique is also applicable to the <xref:System.Windows.Forms.ListBox> control — you can substitute a <xref:System.Windows.Forms.ListBox> for the <xref:System.Windows.Forms.ComboBox>.</span></span>  
  
-   <span data-ttu-id="7c35e-113"><xref:System.Windows.Forms?displayProperty=nameWithType> 및 <xref:System.Drawing?displayProperty=nameWithType> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="7c35e-113">References to the <xref:System.Windows.Forms?displayProperty=nameWithType> and <xref:System.Drawing?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c35e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c35e-114">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox.DrawItem>  
 <xref:System.Windows.Forms.DrawItemEventArgs>  
 <xref:System.Windows.Forms.ComboBox.MeasureItem>  
 [<span data-ttu-id="7c35e-115">소유자 그리기 지원이 기본 제공되는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7c35e-115">Controls with Built-In Owner-Drawing Support</span></span>](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)  
 [<span data-ttu-id="7c35e-116">ListBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7c35e-116">ListBox Control</span></span>](../../../../docs/framework/winforms/controls/listbox-control-windows-forms.md)  
 [<span data-ttu-id="7c35e-117">ComboBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7c35e-117">ComboBox Control</span></span>](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)

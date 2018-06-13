---
title: '방법: TextBox에서 줄 컬렉션 가져오기'
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: 64187527da3cfb97343e2036338822d479dd997a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552742"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="4e1fa-102">방법: TextBox에서 줄 컬렉션 가져오기</span><span class="sxs-lookup"><span data-stu-id="4e1fa-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="4e1fa-103">컬렉션에서 텍스트 줄을 가져오는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="4e1fa-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e1fa-104">예제</span><span class="sxs-lookup"><span data-stu-id="4e1fa-104">Example</span></span>  
 <span data-ttu-id="4e1fa-105">다음 예제에서는 사용 하는 간단한 메서드는 <xref:System.Windows.Controls.TextBox> 인수 및 반환은 <xref:System.Collections.Specialized.StringCollection> 에서 텍스트의 줄을 포함 하는 **TextBox**합니다.</span><span class="sxs-lookup"><span data-stu-id="4e1fa-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="4e1fa-106"><xref:System.Windows.Controls.TextBox.LineCount%2A> 속성의 현재 줄 수를 확인을 사용 하는 **TextBox**, 및 <xref:System.Windows.Controls.TextBox.GetLineText%2A> 메서드는 다음 각 줄을 추출 하 고 줄의 컬렉션에 추가 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e1fa-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="4e1fa-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e1fa-107">See Also</span></span>  
 [<span data-ttu-id="4e1fa-108">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="4e1fa-108">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="4e1fa-109">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="4e1fa-109">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)

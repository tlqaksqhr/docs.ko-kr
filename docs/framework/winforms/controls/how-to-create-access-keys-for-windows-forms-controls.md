---
title: "방법: Windows Forms 컨트롤에 대한 선택키 만들기"
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
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81aa68a65d09b073b117f4d96dfc06e614d68aea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="abcd4-102">방법: Windows Forms 컨트롤에 대한 선택키 만들기</span><span class="sxs-lookup"><span data-stu-id="abcd4-102">How to: Create Access Keys for Windows Forms Controls</span></span>
<span data-ttu-id="abcd4-103">*선택 키* 은 메뉴, 메뉴 항목 또는 예: 단추 컨트롤의 레이블 텍스트에 밑줄이 그어진된 문자.</span><span class="sxs-lookup"><span data-stu-id="abcd4-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="abcd4-104">액세스 키가 있는 사용자 "" 단추를 클릭 수 미리 정의 된 선택 키와 함께에서 ALT 키를 눌러 합니다.</span><span class="sxs-lookup"><span data-stu-id="abcd4-104">With an access key, the user can "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="abcd4-105">예를 들어, 단추는 폼을 인쇄 하는 프로시저를 실행 하는 경우 일부 이므로 해당 `Text` 속성이 "Print"로 설정 된 "p" 하면 "P" 단추 텍스트에는 런타임 시 밑줄이 그어집니다 전에 앰퍼샌드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="abcd4-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="abcd4-106">사용자는 ALT + P를 눌러 단추와 연결 된 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abcd4-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="abcd4-107">포커스를 받을 수 없는 컨트롤에 대 한 선택 키를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abcd4-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="abcd4-108">컨트롤에 대 한 선택 키를 만들려면</span><span class="sxs-lookup"><span data-stu-id="abcd4-108">To create an access key for a control</span></span>  
  
1.  <span data-ttu-id="abcd4-109">설정의 `Text` 앰퍼샌드가 포함 하는 문자열 (&) 문자 바로 가기로 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="abcd4-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="abcd4-110">앰퍼샌드 캡션에 해지지 않도록 선택 키를 포함 하려면 앰퍼샌드를 두 번 포함 (& &).</span><span class="sxs-lookup"><span data-stu-id="abcd4-110">To include an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="abcd4-111">앰퍼샌드 캡션에 나타나고 문자를 사용 하지는 밑줄이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abcd4-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abcd4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abcd4-112">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="abcd4-113">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="abcd4-113">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="abcd4-114">방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정</span><span class="sxs-lookup"><span data-stu-id="abcd4-114">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="abcd4-115">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="abcd4-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)

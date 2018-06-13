---
title: '방법: Windows Forms 대화 상자 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, displaying
- Windows Forms dialog boxes [Windows Forms], displaying
- Windows Forms, calling one form from another
- dialog boxes [Windows Forms], displaying for Windows Forms
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
ms.openlocfilehash: a25fe86c4dde1fed69e192956d77615bf2a70402
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537426"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="1b3b0-102">방법: Windows Forms 대화 상자 표시</span><span class="sxs-lookup"><span data-stu-id="1b3b0-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="1b3b0-103">마찬가지로 응용 프로그램에서 다른 폼을 표시할 때 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b3b0-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="1b3b0-104">시작 폼 응용 프로그램이 실행 될 때 자동으로 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b3b0-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="1b3b0-105">두 번째 폼 또는 대화 상자가 응용 프로그램에 표시 되도록 로드 하 고 표시 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b3b0-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="1b3b0-106">마찬가지로, 폼 또는 대화 상자 사라지게 하려면, 언로드 하거나 숨길 수는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b3b0-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="1b3b0-107">대화 상자를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="1b3b0-107">To display a dialog box</span></span>  
  
1.  <span data-ttu-id="1b3b0-108">대화 상자를 열려면 원하는 이벤트 처리기로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b3b0-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="1b3b0-109">이 메뉴 명령을 선택 단추를 클릭할 때 또는 다른 이벤트가 발생할 때 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b3b0-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2.  <span data-ttu-id="1b3b0-110">이벤트 처리기에서 대화 상자를 열려면 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b3b0-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="1b3b0-111">이 예제에서는 대화 상자를 표시 하는 단추 클릭 이벤트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b3b0-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:   
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```

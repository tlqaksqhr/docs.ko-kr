---
title: "SaveFileDialog 구성 요소 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1505e2bc31afb4f44f0d635b06624528cb16ba15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="d9047-102">SaveFileDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d9047-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="d9047-103">Windows Forms <xref:System.Windows.Forms.SaveFileDialog> 구성 요소는 미리 구성된 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="d9047-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="d9047-104">표준와 같습니다 **파일 저장** Windows에서 사용 되는 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="d9047-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="d9047-105"><xref:System.Windows.Forms.CommonDialog> 클래스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9047-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="d9047-106">SaveFileDialog 구성 요소 작업</span><span class="sxs-lookup"><span data-stu-id="d9047-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="d9047-107">사용자가 고유한 대화 상자를 구성 하는 대신 파일을 저장할 수 있도록 간단한 솔루션으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9047-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="d9047-108">표준 Windows 대화 상자를 사용 하 여 기본 기능을 만드는 응용 프로그램은 사용자에 게 즉시 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9047-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="d9047-109">그러나 때 사용 하는 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소를 직접 파일 저장 논리를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9047-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="d9047-110">사용할 수는 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 런타임 시 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9047-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="d9047-111">사용 하 여 읽기/쓰기 모드로 파일을 열 수는 <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d9047-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="d9047-112">폼에 추가 될 때의 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소는 Windows Forms 디자이너 아래쪽에서 트레이에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9047-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9047-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9047-113">See Also</span></span>  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [<span data-ttu-id="d9047-114">SaveFileDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d9047-114">SaveFileDialog Component</span></span>](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)

---
title: 시작 폼이 지정되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 699d20e6afb2335336b3652be5907f0dd72299fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586788"
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="66cbd-102">시작 폼이 지정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="66cbd-102">A startup form has not been specified</span></span>
<span data-ttu-id="66cbd-103">응용 프로그램 사용은 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 클래스 하지만 시작 폼을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66cbd-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="66cbd-104">때문일 수 있습니다는 **응용 프로그램 프레임 워크 사용** 프로젝트 디자이너에서 확인란을 선택 하지만 **시작 폼** 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="66cbd-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="66cbd-105">자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66cbd-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="66cbd-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="66cbd-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="66cbd-107">응용 프로그램에 대 한 시작 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66cbd-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="66cbd-108">자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지(Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66cbd-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2.  <span data-ttu-id="66cbd-109">재정의 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> 설정 하는 메서드는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> 속성 시작 폼을 합니다.</span><span class="sxs-lookup"><span data-stu-id="66cbd-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66cbd-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66cbd-110">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>  
 [<span data-ttu-id="66cbd-111">Visual Basic 응용 프로그램 모델 개요</span><span class="sxs-lookup"><span data-stu-id="66cbd-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)

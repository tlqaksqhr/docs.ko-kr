---
title: Windows Forms 대화 상자
ms.date: 03/30/2017
helpviewer_keywords:
- dialog boxes [Windows Forms], Windows Forms
- Windows Forms dialog boxes
- dialogs [Windows Forms], using in Windows Forms
ms.assetid: d43d022b-451b-490d-9386-dc79d98fbf8a
ms.openlocfilehash: 302e59c607f179869bcf3923c3092e73a1eddc91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539905"
---
# <a name="dialog-boxes-in-windows-forms"></a><span data-ttu-id="5dfd8-102">Windows Forms 대화 상자</span><span class="sxs-lookup"><span data-stu-id="5dfd8-102">Dialog Boxes in Windows Forms</span></span>
<span data-ttu-id="5dfd8-103">대화 상자는 사용자와 상호 작용하고 정보를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dfd8-103">Dialog boxes are used to interact with the user and retrieve information.</span></span> <span data-ttu-id="5dfd8-104">간단히 말해서 대화 상자는 <xref:System.Windows.Forms.FormBorderStyle> 열거형 속성이 `FixedDialog`로 설정된 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="5dfd8-104">In simple terms, a dialog box is a form with its <xref:System.Windows.Forms.FormBorderStyle> enumeration property set to `FixedDialog`.</span></span> <span data-ttu-id="5dfd8-105">Visual Studio에서 Windows Forms 디자이너를 사용 하 여 사용자 고유의 사용자 지정 대화 상자를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfd8-105">You can construct your own custom dialog boxes by using the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="5dfd8-106">`Label`, `Textbox` 및 `Button`과 같은 컨트롤을 추가하여 특정 필요에 맞게 대화 상자를 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfd8-106">Add controls such as `Label`, `Textbox`, and `Button` to customize dialog boxes to your specific needs.</span></span> <span data-ttu-id="5dfd8-107">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 와 같은 미리 정의 된 대화 상자에도 포함 **파일 열기** 및 응용 프로그램에 사용할 수 있는 메시지 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="5dfd8-107">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also includes predefined dialog boxes, such as **File Open** and message boxes, which you can adapt for your own applications.</span></span> <span data-ttu-id="5dfd8-108">자세한 내용은 참조 [대화 상자 컨트롤 및 구성 요소](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfd8-108">For more information, see [Dialog-Box Controls and Components](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5dfd8-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="5dfd8-109">In This Section</span></span>  
 [<span data-ttu-id="5dfd8-110">방법: Windows Forms 대화 상자 표시</span><span class="sxs-lookup"><span data-stu-id="5dfd8-110">How to: Display Dialog Boxes for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-display-dialog-boxes-for-windows-forms.md)  
 <span data-ttu-id="5dfd8-111">대화 상자 표시에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfd8-111">Gives directions for showing dialog boxes.</span></span>  
  
-   <span data-ttu-id="5dfd8-112">[방법: 선택적으로 여러 속성을 사용 하 여 대화 상자 정보 검색](http://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5dfd8-112">[How to: Retrieve Dialog Box Information Selectively Using Multiple Properties](http://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5dfd8-113">[방법: 대화 상자의 부모 폼에서 정보 검색](http://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5dfd8-113">[How to: Retrieve Information from the Parent Form of a Dialog Box](http://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5dfd8-114">[대화 상자에 사용자 입력](http://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5dfd8-114">[User Input to Dialog Boxes](http://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5dfd8-115">[방법: 대화 상자의 결과 검색](http://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5dfd8-115">[How to: Retrieve the Result for Dialog Boxes](http://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5dfd8-116">[연습: 대화 상자 정보를 집합적으로 개체를 사용 하 여 검색](http://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5dfd8-116">[Walkthrough: Retrieving Dialog Box Information Collectively Using Objects](http://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5dfd8-117">[방법: 대화 상자를 닫고 사용자 입력 유지](http://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5dfd8-117">[How to: Close Dialog Boxes and Retain User Input](http://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5dfd8-118">[방법: 디자인 타임에 대화 상자 만들기](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5dfd8-118">[How to: Create Dialog Boxes at Design Time](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5dfd8-119">[방법: 메시지 상자 표시](http://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5dfd8-119">[How to: Display Message Boxes](http://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5dfd8-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="5dfd8-120">Related Sections</span></span>  
 [<span data-ttu-id="5dfd8-121">대화 상자 컨트롤 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5dfd8-121">Dialog-Box Controls and Components</span></span>](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 <span data-ttu-id="5dfd8-122">미리 정의된 대화 상자 컨트롤을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfd8-122">Lists the predefined dialog box controls.</span></span>  
  
 [<span data-ttu-id="5dfd8-123">Windows Forms의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="5dfd8-123">Changing the Appearance of Windows Forms</span></span>](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)  
 <span data-ttu-id="5dfd8-124">Windows Forms 응용 프로그램의 모양을 변경하는 방법에 대해 설명하는 항목의 링크가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfd8-124">Contains links to topics that describe how to change the appearance of Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="5dfd8-125">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="5dfd8-125">TabControl Control Overview</span></span>](../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="5dfd8-126">탭 컨트롤을 대화 상자에 통합하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfd8-126">Explains how you incorporate the tab control into a dialog box.</span></span>

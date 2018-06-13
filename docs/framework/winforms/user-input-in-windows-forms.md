---
title: Windows Forms에 사용자 입력
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard input [Windows Forms], using in Windows Forms
- Windows Forms, user input
- mouse input [Windows Forms], using in Windows Forms
- keyboards [Windows Forms], keyboard input
ms.assetid: 1486075f-1e06-4c9e-82c6-f948331db6d6
ms.openlocfilehash: 2a618dae8d5f2f5ea6a6581fff2758fe8419f511
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537735"
---
# <a name="user-input-in-windows-forms"></a><span data-ttu-id="d27fc-102">Windows Forms에 사용자 입력</span><span class="sxs-lookup"><span data-stu-id="d27fc-102">User Input in Windows Forms</span></span>
<span data-ttu-id="d27fc-103">Windows Forms에는 관련된 Windows 메시지를 처리하는 동안 발생한 이벤트를 기반으로 하는 사용자 입력 모델이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d27fc-103">Windows Forms includes a user input model based on events that are raised while processing related Windows messages.</span></span> <span data-ttu-id="d27fc-104">이 섹션의 항목에서는 특정 작업을 수행하는 방법을 보여 주는 코드 예제를 포함하여 마우스 및 키보드 사용자 입력에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d27fc-104">The topics in this section provide information on mouse and keyboard user input, including code examples that demonstrate how to perform specific tasks.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d27fc-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d27fc-105">In This Section</span></span>  
 [<span data-ttu-id="d27fc-106">Windows Forms 응용 프로그램의 사용자 입력</span><span class="sxs-lookup"><span data-stu-id="d27fc-106">User Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/user-input-in-a-windows-forms-application.md)  
 <span data-ttu-id="d27fc-107">Windows 메시지를 처리하는 메서드와 사용자 입력 이벤트를 개괄적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d27fc-107">Provides an overview of user input events and the methods that process Windows messages.</span></span>  
  
 [<span data-ttu-id="d27fc-108">Windows Forms 응용 프로그램의 키보드 입력</span><span class="sxs-lookup"><span data-stu-id="d27fc-108">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 <span data-ttu-id="d27fc-109">키보드 메시지 처리, 다양한 유형의 키 및 키보드 이벤트에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d27fc-109">Provides information on keyboard message handling, the different types of keys, and the keyboard events.</span></span>  
  
 [<span data-ttu-id="d27fc-110">Windows Forms 응용 프로그램의 마우스 입력</span><span class="sxs-lookup"><span data-stu-id="d27fc-110">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)  
 <span data-ttu-id="d27fc-111">마우스 이벤트와 마우스 커서 및 마우스 캡처를 비롯한 다른 마우스 관련 기능에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d27fc-111">Provides information on the mouse events and other mouse-related features, including mouse cursors and mouse capture.</span></span>  
  
 [<span data-ttu-id="d27fc-112">방법: 코드에서 마우스 및 키보드 이벤트 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="d27fc-112">How to: Simulate Mouse and Keyboard Events in Code</span></span>](../../../docs/framework/winforms/how-to-simulate-mouse-and-keyboard-events-in-code.md)  
 <span data-ttu-id="d27fc-113">마우스 및 키보드 입력을 프로그래밍 방식으로 시뮬레이션하는 여러 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d27fc-113">Demonstrates several different ways to programmatically simulate mouse and keyboard input.</span></span>  
  
 [<span data-ttu-id="d27fc-114">방법: Windows Forms 컨트롤에서 사용자 입력 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="d27fc-114">How to: Handle User Input Events in Windows Forms Controls</span></span>](../../../docs/framework/winforms/how-to-handle-user-input-events-in-windows-forms-controls.md)  
 <span data-ttu-id="d27fc-115">대부분의 사용자 입력 이벤트를 처리하고 각 이벤트에 대한 정보를 보고하는 코드 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d27fc-115">Presents a code example that handles most user input events and reports information about each event.</span></span>  
  
 [<span data-ttu-id="d27fc-116">Windows Forms에서 사용자 입력 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="d27fc-116">User Input Validation in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 <span data-ttu-id="d27fc-117">Windows Forms 응용 프로그램에서 사용자 입력의 유효성을 검사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d27fc-117">Describes the methods to validate user input in Windows Forms applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d27fc-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d27fc-118">Related Sections</span></span>  
 <span data-ttu-id="d27fc-119">또한 참조 [Windows Forms에서 이벤트 처리기 만들기](http://msdn.microsoft.com/library/dacysss4\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="d27fc-119">Also see [Creating Event Handlers in Windows Forms](http://msdn.microsoft.com/library/dacysss4\(v=vs.110\)).</span></span>

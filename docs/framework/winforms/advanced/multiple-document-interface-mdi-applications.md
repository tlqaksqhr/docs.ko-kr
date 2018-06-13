---
title: MDI 응용 프로그램
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 3fa6f2517b52ecaaf4ad9db4f0de55908eac4c96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523970"
---
# <a name="multiple-document-interface-mdi-applications"></a><span data-ttu-id="04dde-102">MDI 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="04dde-102">Multiple-Document Interface (MDI) Applications</span></span>
<span data-ttu-id="04dde-103">(Mdi 다중) 다중 문서 인터페이스 응용 프로그램을 사용 하는 별도 창에 표시 되는 각 문서와 같은 시간에 여러 문서를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04dde-103">Multiple-document interface (MDI) applications enable you to display multiple documents at the same time, with each document displayed in its own window.</span></span> <span data-ttu-id="04dde-104">MDI 응용 프로그램 창 또는 문서 간 전환에 대 한 하위 메뉴가 있는 창 메뉴 항목이 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="04dde-104">MDI applications often have a Window menu item with submenus for switching between windows or documents.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04dde-105">Windows Forms에서 MDI 폼 및 단일 문서 인터페이스 (SDI) 창 간에 몇 가지 동작 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04dde-105">There are some behavior differences between MDI forms and single-document interface (SDI) windows in Windows Forms.</span></span> <span data-ttu-id="04dde-106">`Opacity` 속성 MDI 자식 폼의 모양에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04dde-106">The `Opacity` property does not affect the appearance of MDI child forms.</span></span> <span data-ttu-id="04dde-107">또한는 <xref:System.Windows.Forms.Form.CenterToParent%2A> 메서드 MDI 자식 폼의 동작에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04dde-107">Additionally, the <xref:System.Windows.Forms.Form.CenterToParent%2A> method does not affect the behavior of MDI child forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04dde-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="04dde-108">In This Section</span></span>  
 [<span data-ttu-id="04dde-109">방법: MDI 상위 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="04dde-109">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 <span data-ttu-id="04dde-110">MDI 응용 프로그램 내에서 여러 문서에 대 한 컨테이너를 만들기 위한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="04dde-110">Gives directions for creating the container for the multiple documents within an MDI application.</span></span>  
  
 [<span data-ttu-id="04dde-111">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="04dde-111">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 <span data-ttu-id="04dde-112">MDI 부모 폼 내에서 작동 하는 하나 이상의 창을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="04dde-112">Gives directions for creating one or more windows that operate within an MDI parent form.</span></span>  
  
 [<span data-ttu-id="04dde-113">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="04dde-113">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 <span data-ttu-id="04dde-114">포커스가 있는 자식 창 확인 하기 위한 지침을 제공 (및 해당 내용을 클립보드에 보내는).</span><span class="sxs-lookup"><span data-stu-id="04dde-114">Gives directions for verifying the child window that has focus (and sending its contents to the Clipboard).</span></span>  
  
 [<span data-ttu-id="04dde-115">방법: 활성 MDI 자식으로 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="04dde-115">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 <span data-ttu-id="04dde-116">활성 자식 창으로 정보를 전송에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="04dde-116">Gives directions for transporting information to the active child window.</span></span>  
  
 [<span data-ttu-id="04dde-117">방법: MDI 자식 양식 정렬</span><span class="sxs-lookup"><span data-stu-id="04dde-117">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)  
 <span data-ttu-id="04dde-118">바둑판식 배열, 계단식 또는 자식 창을 MDI 응용 프로그램의 정렬에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="04dde-118">Gives directions for tiling, cascading, or arranging the child windows of an MDI application.</span></span>

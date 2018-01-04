---
title: "내게 필요한 옵션 지침을 지원하는 Windows Forms 컨트롤의 속성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 967b4a0e883338c756aceef37d11edecfb978527
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="39702-102">내게 필요한 옵션 지침을 지원하는 Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="39702-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="39702-103">표준 Windows Forms 도구 상자에서 컨트롤에 키보드 포커스 노출을 노출 및 화면 요소를 포함 하 여 내게 필요한 옵션 지침을 여러 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="39702-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="39702-104">내게 필요한 옵션에 대 한 미리 계획</span><span class="sxs-lookup"><span data-stu-id="39702-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="39702-105">컨트롤의 속성은 다음 표에 나와 있는 것 처럼 다른 내게 필요한 옵션 지침을 지 원하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39702-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="39702-106">또한 메뉴를 사용 하면 프로그램 기능에 대 한 액세스를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39702-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="39702-107">컨트롤 속성</span><span class="sxs-lookup"><span data-stu-id="39702-107">Control Property</span></span>|<span data-ttu-id="39702-108">내게 필요한 옵션에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="39702-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="39702-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="39702-109">AccessibleDescription</span></span>|<span data-ttu-id="39702-110">화면 판독기와 같은 접근성 보조 기능에 대 한 설명을 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39702-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="39702-111">접근성 보조 기능은 장애가 있는 사용자가 컴퓨터를 보다 효율적으로 사용하도록 돕는 특수 프로그램 및 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="39702-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="39702-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="39702-112">AccessibleName</span></span>|<span data-ttu-id="39702-113">접근성 보조 기능에 보고 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="39702-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="39702-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="39702-114">AccessibleRole</span></span>|<span data-ttu-id="39702-115">사용자 인터페이스에서 해당 요소의 용도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="39702-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="39702-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="39702-116">TabIndex</span></span>|<span data-ttu-id="39702-117">폼을 탐색할 수 있는 탐색 경로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="39702-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="39702-118">연결 된 레이블을 바로 앞에 두 탭 순서에서 해당 텍스트 상자와 같은 내장 레이블이 없는 컨트롤에 대 한 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="39702-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="39702-119">텍스트</span><span class="sxs-lookup"><span data-stu-id="39702-119">Text</span></span>|<span data-ttu-id="39702-120">선택 키를 만들려면 "&" 문자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="39702-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="39702-121">선택 키를 사용 하 여 기능에 대 한 문서화 된 키보드 액세스를 제공 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="39702-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="39702-122">글꼴 크기</span><span class="sxs-lookup"><span data-stu-id="39702-122">Font Size</span></span>|<span data-ttu-id="39702-123">글꼴 크기를 조정할 수 없는 경우 다음 설정 해야 10 포인트 이상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="39702-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="39702-124">폼의 글꼴 크기 설정 되 고 나면 이후에 폼에 추가 된 모든 컨트롤 같은 크기를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="39702-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="39702-125">Forecolor</span><span class="sxs-lookup"><span data-stu-id="39702-125">Forecolor</span></span>|<span data-ttu-id="39702-126">이 속성을 기본값으로 설정 된 사용자의 색 기본 설정은 폼에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39702-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="39702-127">Backcolor</span><span class="sxs-lookup"><span data-stu-id="39702-127">Backcolor</span></span>|<span data-ttu-id="39702-128">이 속성을 기본값으로 설정 된 사용자의 색 기본 설정은 폼에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39702-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="39702-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="39702-129">BackgroundImage</span></span>|<span data-ttu-id="39702-130">이 속성 텍스트를 더 쉽게 읽을 수 있도록 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="39702-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39702-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39702-131">See Also</span></span>  
 [<span data-ttu-id="39702-132">연습: 내게 필요한 옵션이 지원되는 Windows 기반 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="39702-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)

---
title: My.Settings 개체
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f744460f8ea6c6c7f5c8c5e1658bd357e910def
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="mysettings-object"></a><span data-ttu-id="92b5e-102">My.Settings 개체</span><span class="sxs-lookup"><span data-stu-id="92b5e-102">My.Settings Object</span></span>
<span data-ttu-id="92b5e-103">응용 프로그램의 설정에 액세스 하기 위한 메서드와 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92b5e-104">설명</span><span class="sxs-lookup"><span data-stu-id="92b5e-104">Remarks</span></span>  
 <span data-ttu-id="92b5e-105">`My.Settings` 개체 응용 프로그램의 설정에 대 한 액세스를 제공 하 고 동적으로 저장 하 고 속성 설정 및 응용 프로그램에 대 한 기타 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="92b5e-106">자세한 내용은 [응용 프로그램 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92b5e-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="92b5e-107">속성</span><span class="sxs-lookup"><span data-stu-id="92b5e-107">Properties</span></span>  
 <span data-ttu-id="92b5e-108">`My.Settings` 개체의 속성을 통해 응용 프로그램 설정에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="92b5e-109">를 추가 하거나 설정을 제거는 **설정 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="92b5e-110">각 설정에는 **이름**, **형식**, **범위**, 및 **값**, 이러한 설정에 따라 결정 하 고 어떻게 각 설정에 액세스 하는 속성 에 표시 된 `My.Settings` 개체:</span><span class="sxs-lookup"><span data-stu-id="92b5e-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="92b5e-111">**이름** 속성의 이름을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="92b5e-112">**형식** 속성의 유형을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="92b5e-113">**범위** 읽기 전용 속성 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="92b5e-114">값이 **응용 프로그램**, 읽기 전용 이면 값이 속성은 **사용자**, 속성은 읽기 / 쓰기입니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="92b5e-115">**값** 속성의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="92b5e-116">메서드</span><span class="sxs-lookup"><span data-stu-id="92b5e-116">Methods</span></span>  
  
|<span data-ttu-id="92b5e-117">메서드</span><span class="sxs-lookup"><span data-stu-id="92b5e-117">Method</span></span>|<span data-ttu-id="92b5e-118">설명</span><span class="sxs-lookup"><span data-stu-id="92b5e-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="92b5e-119">마지막으로 저장 된 값의 사용자 설정을 다시 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="92b5e-120">현재 사용자 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="92b5e-121">`My.Settings` 개체도 고급 속성과에서 상속 된 메서드를 제공는 <xref:System.Configuration.ApplicationSettingsBase> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="92b5e-122">작업</span><span class="sxs-lookup"><span data-stu-id="92b5e-122">Tasks</span></span>  
 <span data-ttu-id="92b5e-123">다음 표에서 관련 된 작업의 예를 보여 줍니다.는 `My.Settings` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="92b5e-124">후</span><span class="sxs-lookup"><span data-stu-id="92b5e-124">To</span></span>|<span data-ttu-id="92b5e-125">참조</span><span class="sxs-lookup"><span data-stu-id="92b5e-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="92b5e-126">응용 프로그램 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="92b5e-126">Read an application setting</span></span>|[<span data-ttu-id="92b5e-127">방법: Visual Basic에서 응용 프로그램 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="92b5e-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="92b5e-128">사용자 설정을 변경</span><span class="sxs-lookup"><span data-stu-id="92b5e-128">Change a user setting</span></span>|[<span data-ttu-id="92b5e-129">방법: Visual Basic에서 사용자 설정 변경</span><span class="sxs-lookup"><span data-stu-id="92b5e-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="92b5e-130">사용자 설정 유지</span><span class="sxs-lookup"><span data-stu-id="92b5e-130">Persist user settings</span></span>|[<span data-ttu-id="92b5e-131">방법: Visual Basic에서 사용자 설정 유지</span><span class="sxs-lookup"><span data-stu-id="92b5e-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="92b5e-132">사용자 설정에 대 한 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="92b5e-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="92b5e-133">방법: Visual Basic에서 사용자 설정의 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="92b5e-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="92b5e-134">예제</span><span class="sxs-lookup"><span data-stu-id="92b5e-134">Example</span></span>  
 <span data-ttu-id="92b5e-135">이 예제에서는 `Nickname` 설정의 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 <span data-ttu-id="92b5e-136">이 예제가 작동하려면 응용 프로그램에 `String` 형식의 `Nickname` 설정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5e-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92b5e-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92b5e-137">See Also</span></span>  
 <xref:System.Configuration.ApplicationSettingsBase>  
 [<span data-ttu-id="92b5e-138">방법: Visual Basic에서 응용 프로그램 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="92b5e-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [<span data-ttu-id="92b5e-139">방법: Visual Basic에서 사용자 설정 변경</span><span class="sxs-lookup"><span data-stu-id="92b5e-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [<span data-ttu-id="92b5e-140">방법: Visual Basic에서 사용자 설정 유지</span><span class="sxs-lookup"><span data-stu-id="92b5e-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [<span data-ttu-id="92b5e-141">방법: Visual Basic에서 사용자 설정의 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="92b5e-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [<span data-ttu-id="92b5e-142">응용 프로그램 설정 관리(.NET)</span><span class="sxs-lookup"><span data-stu-id="92b5e-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

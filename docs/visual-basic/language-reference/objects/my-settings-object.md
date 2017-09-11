---
title: "My.Settings 개체 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4d6ee6d2d54c0e3a4af3b7cdec5f81166ce3ddce
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="mysettings-object"></a><span data-ttu-id="52a0c-102">My.Settings 개체</span><span class="sxs-lookup"><span data-stu-id="52a0c-102">My.Settings Object</span></span>
<span data-ttu-id="52a0c-103">응용 프로그램의 설정에 액세스 하기 위한 메서드와 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52a0c-104">주의</span><span class="sxs-lookup"><span data-stu-id="52a0c-104">Remarks</span></span>  
 <span data-ttu-id="52a0c-105">`My.Settings` 개체 응용 프로그램의 설정에 대 한 액세스를 제공 하 고 동적으로 저장 하 고 속성 설정 및 응용 프로그램에 대 한 기타 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="52a0c-106">자세한 내용은 참조 [응용 프로그램 설정 관리 (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)합니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-106">For more information, see [Managing Application Settings (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="52a0c-107">속성</span><span class="sxs-lookup"><span data-stu-id="52a0c-107">Properties</span></span>  
 <span data-ttu-id="52a0c-108">속성은 `My.Settings` 개체 응용 프로그램의 설정에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="52a0c-109">를 추가 하거나 설정을 제거는 **설정 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="52a0c-110">각 설정에는 **이름**, **형식**, **범위**, 및 **값**, 이러한 설정은 각 설정에 액세스 하는 속성에 표시 되는 방식을 결정 하 고는 `My.Settings` 개체:</span><span class="sxs-lookup"><span data-stu-id="52a0c-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="52a0c-111">**이름** 속성의 이름을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="52a0c-112">**형식** 속성의 유형을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="52a0c-113">**범위** 읽기 전용 속성 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="52a0c-114">값이 **응용 프로그램**, 속성은 읽기 전용 이면 값이 **사용자**, 속성은 읽기 / 쓰기입니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="52a0c-115">**값** 속성의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52a0c-116">메서드</span><span class="sxs-lookup"><span data-stu-id="52a0c-116">Methods</span></span>  
  
|<span data-ttu-id="52a0c-117">메서드</span><span class="sxs-lookup"><span data-stu-id="52a0c-117">Method</span></span>|<span data-ttu-id="52a0c-118">설명</span><span class="sxs-lookup"><span data-stu-id="52a0c-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="52a0c-119">마지막으로 저장 된 값에서 사용자 설정을 다시 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="52a0c-120">현재 사용자 설정을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="52a0c-121">`My.Settings` 고급 속성 및 메서드를 <xref:System.Configuration.ApplicationSettingsBase>클래스</xref:System.Configuration.ApplicationSettingsBase> 에서 상속 된 개체 제공</span><span class="sxs-lookup"><span data-stu-id="52a0c-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="52a0c-122">작업</span><span class="sxs-lookup"><span data-stu-id="52a0c-122">Tasks</span></span>  
 <span data-ttu-id="52a0c-123">다음 표에서 관련 된 작업의 예제는 `My.Settings` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="52a0c-124">후</span><span class="sxs-lookup"><span data-stu-id="52a0c-124">To</span></span>|<span data-ttu-id="52a0c-125">참조</span><span class="sxs-lookup"><span data-stu-id="52a0c-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="52a0c-126">응용 프로그램 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="52a0c-126">Read an application setting</span></span>|[<span data-ttu-id="52a0c-127">방법: Visual Basic의 응용 프로그램 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="52a0c-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="52a0c-128">사용자 설정 변경</span><span class="sxs-lookup"><span data-stu-id="52a0c-128">Change a user setting</span></span>|[<span data-ttu-id="52a0c-129">방법: Visual Basic에서 사용자 설정 변경</span><span class="sxs-lookup"><span data-stu-id="52a0c-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="52a0c-130">사용자 설정 유지</span><span class="sxs-lookup"><span data-stu-id="52a0c-130">Persist user settings</span></span>|[<span data-ttu-id="52a0c-131">방법: Visual Basic에서 사용자 설정 유지</span><span class="sxs-lookup"><span data-stu-id="52a0c-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="52a0c-132">사용자 설정에 대 한 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="52a0c-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="52a0c-133">방법: Visual Basic에서 사용자 설정의 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="52a0c-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="52a0c-134">예제</span><span class="sxs-lookup"><span data-stu-id="52a0c-134">Example</span></span>  
 <span data-ttu-id="52a0c-135">값을 표시 하는이 예제는 `Nickname` 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 <span data-ttu-id="52a0c-136">[!code-vb[VbVbalrMyResources #&14;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="52a0c-136">[!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]</span></span>  
  
 <span data-ttu-id="52a0c-137">이 예제가 작동 하려면 응용 프로그램 있어야는 `Nickname` 유형의 설정 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="52a0c-137">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a0c-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52a0c-138">See Also</span></span>  
 <span data-ttu-id="52a0c-139"><xref:System.Configuration.ApplicationSettingsBase></xref:System.Configuration.ApplicationSettingsBase></span><span class="sxs-lookup"><span data-stu-id="52a0c-139"><xref:System.Configuration.ApplicationSettingsBase></span></span>   
<span data-ttu-id="52a0c-140"> [방법: Visual Basic의 응용 프로그램 설정 읽기](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span><span class="sxs-lookup"><span data-stu-id="52a0c-140"> [How to: Read Application Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span></span>  
<span data-ttu-id="52a0c-141"> [방법: Visual Basic에서 사용자 설정 변경](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="52a0c-141"> [How to: Change User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span></span>  
<span data-ttu-id="52a0c-142"> [방법: Visual Basic에서 사용자 설정 유지](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="52a0c-142"> [How to: Persist User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span></span>  
<span data-ttu-id="52a0c-143"> [방법: Visual Basic에서 사용자 설정의 속성 표 만들기](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="52a0c-143"> [How to: Create Property Grids for User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span></span>  
<span data-ttu-id="52a0c-144"> [응용 프로그램 설정 관리(.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)</span><span class="sxs-lookup"><span data-stu-id="52a0c-144"> [Managing Application Settings (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)</span></span>

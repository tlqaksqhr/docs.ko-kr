---
title: "방법: Visual Basic에서 사용자 설정의 속성 표 만들기"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object, creating property grids for user settings
- user settings, creating property grids
- property grids, creating for user settings
- property grids
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
caps.latest.revision: 13
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c21b458f9c28f4d25e5b0d8099b9a5255f31ac52
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-property-grids-for-user-settings-in-visual-basic"></a><span data-ttu-id="49f47-102">방법: Visual Basic에서 사용자 설정의 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="49f47-102">How to: Create Property Grids for User Settings in Visual Basic</span></span>
<span data-ttu-id="49f47-103"><xref:System.Windows.Forms.PropertyGrid> 컨트롤을 `My.Settings` 개체의 사용자 설정 속성으로 채워 사용자 설정에 대한 속성 표를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-103">You can create a property grid for user settings by populating a <xref:System.Windows.Forms.PropertyGrid> control with the user setting properties of the `My.Settings` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49f47-104">이 예제가 작동하려면 응용 프로그램에 해당 사용자 설정이 구성되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-104">In order for this example to work, your application must have its user settings configured.</span></span> <span data-ttu-id="49f47-105">자세한 내용은 [응용 프로그램 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49f47-105">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
 <span data-ttu-id="49f47-106">`My.Settings` 개체는 각 설정을 속성으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-106">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="49f47-107">속성 이름은 설정 이름과 같고 속성 형식은 설정 형식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-107">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="49f47-108">설정의 **범위**는 속성이 읽기 전용인지 여부를 결정합니다. **응용 프로그램** 범위 설정의 속성은 읽기 전용이지만 **사용자** 범위 설정의 속성은 읽기-쓰기입니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-108">The setting's **Scope** determines if the property is read-only; the property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="49f47-109">자세한 내용은 [My.Settings 개체](../../../../visual-basic/language-reference/objects/my-settings-object.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49f47-109">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49f47-110">런타임에 응용 프로그램 범위 설정의 값을 변경하거나 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-110">You cannot change or save the values of application-scope settings at run time.</span></span> <span data-ttu-id="49f47-111">**프로젝트 디자이너**를 통해 또는 응용 프로그램의 구성 파일을 편집하여 응용 프로그램을 만들 때만 응용 프로그램 범위 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-111">Application-scope settings can be changed only when creating the application (through the **Project Designer**) or by editing the application's configuration file.</span></span> <span data-ttu-id="49f47-112">자세한 내용은 [응용 프로그램 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49f47-112">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
 <span data-ttu-id="49f47-113">이 예제에서는 <xref:System.Windows.Forms.PropertyGrid> 컨트롤을 사용하여 `My.Settings` 개체의 사용자 설정 속성에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-113">This example uses a <xref:System.Windows.Forms.PropertyGrid> control to access the user-setting properties of the `My.Settings` object.</span></span> <span data-ttu-id="49f47-114">기본적으로 <xref:System.Windows.Forms.PropertyGrid>는 `My.Settings` 개체의 모든 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-114">By default, the <xref:System.Windows.Forms.PropertyGrid> shows all the properties of the `My.Settings` object.</span></span> <span data-ttu-id="49f47-115">하지만 사용자 설정 속성에는 <xref:System.Configuration.UserScopedSettingAttribute> 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-115">However, the user-setting properties have the <xref:System.Configuration.UserScopedSettingAttribute> attribute.</span></span> <span data-ttu-id="49f47-116">이 예제에서는 <xref:System.Windows.Forms.PropertyGrid>의 <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> 속성을 <xref:System.Configuration.UserScopedSettingAttribute>로 설정하여 사용자 설정 속성만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-116">This example sets the <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> property of the <xref:System.Windows.Forms.PropertyGrid> to <xref:System.Configuration.UserScopedSettingAttribute> to display only the user-setting properties.</span></span>  
  
### <a name="to-add-a-user-setting-property-grid"></a><span data-ttu-id="49f47-117">사용자 설정 속성 표를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="49f47-117">To add a user setting property grid</span></span>  
  
1.  <span data-ttu-id="49f47-118">**도구 상자**에서 응용 프로그램의 디자인 화면(여기서는 `Form1`)으로 **PropertyGrid** 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-118">Add the **PropertyGrid** control from the **Toolbox** to the design surface for your application, assumed here to be `Form1`.</span></span>  
  
     <span data-ttu-id="49f47-119">속성 표 컨트롤의 기본 이름은 `PropertyGrid1`입니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-119">The default name of the property-grid control is `PropertyGrid1`.</span></span>  
  
2.  <span data-ttu-id="49f47-120">`Form1`의 디자인 화면을 두 번 클릭하여 양식 로드 이벤트 처리기에 대한 코드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-120">Double-click the design surface for `Form1` to open the code for the form-load event handler.</span></span>  
  
3.  <span data-ttu-id="49f47-121">`My.Settings` 개체를 속성 표에 대해 선택된 개체로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-121">Set the `My.Settings` object as the selected object for the property grid.</span></span>  
  
     <span data-ttu-id="49f47-122">[!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="49f47-122">[!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]</span></span>  
  
4.  <span data-ttu-id="49f47-123">사용자 설정만 표시하도록 속성 표를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-123">Configure the property grid to show only the user settings.</span></span>  
  
     <span data-ttu-id="49f47-124">[!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="49f47-124">[!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49f47-125">응용 프로그램 범위 설정만 표시하려면 <xref:System.Configuration.UserScopedSettingAttribute> 대신 <xref:System.Configuration.ApplicationScopedSettingAttribute> 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-125">To show only the application-scope settings, use the <xref:System.Configuration.ApplicationScopedSettingAttribute> attribute instead of  <xref:System.Configuration.UserScopedSettingAttribute>.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="49f47-126">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="49f47-126">Robust Programming</span></span>  
 <span data-ttu-id="49f47-127">응용 프로그램이 종료될 때 사용자 설정이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-127">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="49f47-128">설정을 즉시 저장하려면 `My.Settings.Save` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="49f47-128">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="49f47-129">자세한 내용은 [방법: Visual Basic에서 사용자 설정 유지](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49f47-129">For more information, see [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f47-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49f47-130">See Also</span></span>  
 <span data-ttu-id="49f47-131">[My.Settings 개체](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span><span class="sxs-lookup"><span data-stu-id="49f47-131">[My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md) </span></span>  
 <span data-ttu-id="49f47-132">[방법: Visual Basic에서 응용 프로그램 설정 읽기](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span><span class="sxs-lookup"><span data-stu-id="49f47-132">[How to: Read Application Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span></span>  
 <span data-ttu-id="49f47-133">[방법: Visual Basic에서 사용자 설정 변경](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="49f47-133">[How to: Change User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span></span>  
 <span data-ttu-id="49f47-134">[방법: Visual Basic에서 사용자 설정 유지](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="49f47-134">[How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span></span>  
 [<span data-ttu-id="49f47-135">응용 프로그램 설정 관리(.NET)</span><span class="sxs-lookup"><span data-stu-id="49f47-135">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)


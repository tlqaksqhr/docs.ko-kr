---
title: "방법: Visual Basic에서 응용 프로그램 설정 읽기"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- reading application settings
- My.Settings object [Visual Basic], reading application settings
- application settings [Visual Basic], reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ea6cfc529262053daf7c8111271de2c51e9cab4e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-application-settings-in-visual-basic"></a><span data-ttu-id="44f0e-102">방법: Visual Basic에서 응용 프로그램 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="44f0e-102">How to: Read Application Settings in Visual Basic</span></span>
<span data-ttu-id="44f0e-103">`My.Settings` 개체에서 설정의 속성에 액세스하여 사용자 설정을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44f0e-103">You can read a user setting by accessing the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="44f0e-104">`My.Settings` 개체는 각 설정을 속성으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="44f0e-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="44f0e-105">속성 이름은 설정 이름과 같고 속성 형식은 설정 형식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44f0e-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="44f0e-106">설정의 **범위**는 속성이 읽기 전용인지 여부를 나타냅니다. **응용 프로그램** 범위 설정의 속성은 읽기 전용이지만 **사용자** 범위 설정의 속성은 읽기-쓰기입니다.</span><span class="sxs-lookup"><span data-stu-id="44f0e-106">The setting's **Scope** indicates if the property is read-only; the property for an **Application** scope setting is read-only, while the property for a **User** scope setting is read-write.</span></span> <span data-ttu-id="44f0e-107">자세한 내용은 [My.Settings 개체](../../../../visual-basic/language-reference/objects/my-settings-object.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44f0e-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44f0e-108">예제</span><span class="sxs-lookup"><span data-stu-id="44f0e-108">Example</span></span>  
 <span data-ttu-id="44f0e-109">이 예제에서는 `Nickname` 설정의 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="44f0e-109">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]  
  
 <span data-ttu-id="44f0e-110">이 예제가 작동하려면 응용 프로그램에 `String` 형식의 `Nickname` 설정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44f0e-110">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span> <span data-ttu-id="44f0e-111">자세한 내용은 [응용 프로그램 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44f0e-111">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f0e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44f0e-112">See Also</span></span>  
 [<span data-ttu-id="44f0e-113">My.Settings 개체</span><span class="sxs-lookup"><span data-stu-id="44f0e-113">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="44f0e-114">방법: Visual Basic에서 사용자 설정 변경</span><span class="sxs-lookup"><span data-stu-id="44f0e-114">How to: Change User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [<span data-ttu-id="44f0e-115">방법: Visual Basic에서 사용자 설정 유지</span><span class="sxs-lookup"><span data-stu-id="44f0e-115">How to: Persist User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [<span data-ttu-id="44f0e-116">방법: Visual Basic에서 사용자 설정의 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="44f0e-116">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [<span data-ttu-id="44f0e-117">응용 프로그램 설정 관리(.NET)</span><span class="sxs-lookup"><span data-stu-id="44f0e-117">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)

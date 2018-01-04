---
title: "방법: 디자인 타임에 새 설정 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04b86579f45c5a357f8759bf36ae41f7a5c6e98b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="794dd-102">방법: 디자인 타임에 새 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="794dd-102">How To: Create a New Setting at Design Time</span></span>
<span data-ttu-id="794dd-103">설정 디자이너를 사용 하 여 디자인 타임에 새 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794dd-103">You can create a new setting at design time by using the Settings designer.</span></span> <span data-ttu-id="794dd-104">설정 디자이너는 새 설정을 만들고 이러한 설정에 대 한 속성을 지정할 수 있도록 표 스타일 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="794dd-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="794dd-105">이름, 값, 유형 및 새 설정에 대 한 범위를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="794dd-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="794dd-106">설정을 만든 후에 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794dd-106">Once a setting is created, it is accessible in code.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="794dd-107">C#에서 디자인 타임에 새 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="794dd-107">To create a new setting at design time in C#</span></span>  
  
1.  <span data-ttu-id="794dd-108">**솔루션 탐색기**를 확장 하 고는 **속성** 프로젝트의 노드.</span><span class="sxs-lookup"><span data-stu-id="794dd-108">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>  
  
2.  <span data-ttu-id="794dd-109">새 설정을 추가 하려는.settings 파일을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="794dd-109">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="794dd-110">이 파일에 대 한 기본 이름은 Settings.settings입니다.</span><span class="sxs-lookup"><span data-stu-id="794dd-110">The default name for this file is Settings.settings.</span></span>  
  
3.  <span data-ttu-id="794dd-111">설정 디자이너에서 이름, 값, 형식 및 사용자 설정에 대 한 범위를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="794dd-111">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="794dd-112">각 행에는 단일 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="794dd-112">Each row represents a single setting.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="794dd-113">Visual Basic의 디자인 타임에 새 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="794dd-113">To create a new setting at design time in Visual Basic</span></span>  
  
1.  <span data-ttu-id="794dd-114">**솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="794dd-114">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="794dd-115">에 **속성** 선택 페이지는 **설정을** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="794dd-115">In the **Properties** page, select the **Settings** tab.</span></span>  
  
3.  <span data-ttu-id="794dd-116">설정 디자이너에서 이름, 값, 형식 및 사용자 설정에 대 한 범위를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="794dd-116">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="794dd-117">각 행에는 단일 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="794dd-117">Each row represents a single setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="794dd-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="794dd-118">See Also</span></span>  
 [<span data-ttu-id="794dd-119">응용 프로그램 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="794dd-119">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="794dd-120">응용 프로그램 설정 개요</span><span class="sxs-lookup"><span data-stu-id="794dd-120">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [<span data-ttu-id="794dd-121">방법: 디자인 타임에 기존 설정 값 변경</span><span class="sxs-lookup"><span data-stu-id="794dd-121">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)

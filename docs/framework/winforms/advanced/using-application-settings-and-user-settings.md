---
title: 응용 프로그램 설정 및 사용자 설정 사용
ms.date: 03/30/2017
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: f5231ecc9fb3898d60241ea8a53b509daced8a0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523844"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="aae5f-102">응용 프로그램 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="aae5f-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="aae5f-103">.NET Framework 2.0 부터는 수 만들고 응용 프로그램 실행 세션 간에 유지 되는 값에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="aae5f-104">이러한 값은 라고 *설정을*합니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-104">These values are called *settings*.</span></span> <span data-ttu-id="aae5f-105">설정에는 사용자 기본 설정을 나타낼 수 있습니다 또는 응용 프로그램의 중요 한 정보를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="aae5f-106">예를 들어 일련의 응용 프로그램의 색 구성표에 대 한 사용자 기본 설정을 저장 하는 설정 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="aae5f-107">또는 응용 프로그램을 사용 하는 데이터베이스를 지정 하는 연결 문자열을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="aae5f-108">설정을 통해 개별 사용자의 기본 설정을 저장 하는 프로필을 만들려고 하 고 외부의 코드를 응용 프로그램에 중요 한 정보를 유지 하는 둘 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="aae5f-109">이 단원의 항목에서는 실행 시간 및 디자인 타임에 설정을 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aae5f-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="aae5f-110">In This Section</span></span>  
 [<span data-ttu-id="aae5f-111">방법: 디자인 타임에 새 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="aae5f-111">How To: Create a New Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="aae5f-112">응용 프로그램에 대 한 새 설정을 만들려면 Visual Studio를 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="aae5f-113">방법: 디자인 타임에 기존 설정 값 변경</span><span class="sxs-lookup"><span data-stu-id="aae5f-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="aae5f-114">기존 설정의 값을 변경 하려면 Visual Studio를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="aae5f-115">방법: 응용 프로그램 세션 간 설정 값 변경</span><span class="sxs-lookup"><span data-stu-id="aae5f-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="aae5f-116">응용 프로그램 세션 간에 컴파일된 응용 프로그램 설정의 값을 변경 하는 방법에 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="aae5f-117">방법: C#을 사용하여 런타임에 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="aae5f-117">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="aae5f-118">코드와 C# 설정 읽기를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="aae5f-119">방법: C#을 사용하여 런타임에 사용자 설정 쓰기</span><span class="sxs-lookup"><span data-stu-id="aae5f-119">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="aae5f-120">코드를 사용 하 여 작성 하 고 C#으로 사용자 설정의 값을 저장 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="aae5f-121">방법: C#에서 응용 프로그램에 다중 설정 집합 추가</span><span class="sxs-lookup"><span data-stu-id="aae5f-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="aae5f-122">C#으로 응용 프로그램에 여러 설정 집합을 추가 하는 방법을 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="aae5f-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae5f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aae5f-123">See Also</span></span>  
 [<span data-ttu-id="aae5f-124">Windows Forms에 대한 응용 프로그램 설정</span><span class="sxs-lookup"><span data-stu-id="aae5f-124">Application Settings for Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/application-settings-for-windows-forms.md)

---
title: "방법: C#을 사용하여 런타임에 사용자 설정 쓰기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5966aef77c994d2657bd282ad15e8f59a64eeb47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="b7086-102">방법: C#을 사용하여 런타임에 사용자 설정 쓰기</span><span class="sxs-lookup"><span data-stu-id="b7086-102">How To: Write User Settings at Run Time with C#</span></span> #
<span data-ttu-id="b7086-103">응용 프로그램 범위가 지정된 설정은 읽기 전용이며 응용 프로그램 세션 간에 .config 파일을 변경하여 또는 디자인 타임에만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7086-103">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="b7086-104">그러나 사용자 범위가 지정된 설정은 속성 값을 변경하는 것과 마찬가지로 런타임에 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7086-104">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="b7086-105">새 값은 응용 프로그램 세션 기간 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7086-105">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="b7086-106">Save 메서드를 호출하여 응용 프로그램 세션 간에 설정 변경 내용을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7086-106">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
### <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="b7086-107">방법: C#을 사용하여 런타임에 사용자 설정 쓰기 및 유지</span><span class="sxs-lookup"><span data-stu-id="b7086-107">How To: Write and Persist User Settings at Run Time with C#</span></span>  
  
1.  <span data-ttu-id="b7086-108">아래 예제와 같이 설정에 액세스하고 새 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b7086-108">Access the setting and assign it a new value as shown in this example:</span></span>  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  <span data-ttu-id="b7086-109">응용 프로그램 세션 간에 설정 변경 내용을 유지하려면 아래 예제와 같이 Save 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b7086-109">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     <span data-ttu-id="b7086-110">사용자 설정은 사용자의 로컬 숨겨진 응용 프로그램 데이터 폴더의 하위 폴더 내에 있는 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7086-110">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7086-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7086-111">See Also</span></span>  
 [<span data-ttu-id="b7086-112">응용 프로그램 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="b7086-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="b7086-113">방법: C#을 사용하여 런타임에 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="b7086-113">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
 [<span data-ttu-id="b7086-114">응용 프로그램 설정 개요</span><span class="sxs-lookup"><span data-stu-id="b7086-114">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)

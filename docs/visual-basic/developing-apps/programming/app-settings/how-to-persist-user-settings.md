---
title: "방법: Visual Basic에서 사용자 설정 유지 | Microsoft 문서"
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
- My.Settings object, persisting user settings
- persistence, persisting user settings [Visual Basic]
- user settings, persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
caps.latest.revision: 15
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 53fc5bd08265e4eb28a8bc6a8a145c50d662c494
ms.contentlocale: ko-kr
ms.lasthandoff: 05/24/2017

---
# <a name="how-to-persist-user-settings-in-visual-basic"></a>방법: Visual Basic에서 사용자 설정 유지
`My.Settings.Save` 메서드를 사용하여 사용자 설정에 대한 변경 내용을 유지할 수 있습니다.  
  
 일반적으로 응용 프로그램은 해당 응용 프로그램이 종료될 때 사용자 설정에 대한 변경 내용을 유지하도록 설계되었습니다. 이는 여러 가지 요인에 따라 몇 초마다 설정이 저장될 수 있기 때문입니다.  
  
 자세한 내용은 [My.Settings 개체](../../../../visual-basic/language-reference/objects/my-settings-object.md)를 참조하세요.  
  
> [!NOTE]
>  런타임에 사용자 범위의 값을 변경하고 저장할 수 있지만 응용 프로그램 범위 설정은 읽기 전용이고 프로그래밍 방식으로 변경할 수 없습니다. **프로젝트 디자이너**를 통해 또는 응용 프로그램의 구성 파일을 편집하여 응용 프로그램을 만들 때 응용 프로그램 범위 설정을 변경할 수 있습니다. 자세한 내용은 [응용 프로그램 설정 관리(.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.  
  
## <a name="example"></a>예제  
 이 예제에서는 `LastChanged` 사용자 설정의 값을 변경하고 `My.Settings.Save` 메서드를 호출하여 해당 변경 내용을 저장합니다.  
  
 [!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]  
  
 이 예제가 작동하려면 응용 프로그램에 `Date` 형식의 `LastChanged` 사용자 설정이 있어야 합니다. 자세한 내용은 [응용 프로그램 설정 관리(.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [My.Settings 개체](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [방법: Visual Basic에서 응용 프로그램 설정 읽기](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [방법: Visual Basic에서 사용자 설정 변경](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [방법: Visual Basic에서 사용자 설정의 속성 표 만들기](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [응용 프로그램 설정 관리(.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)

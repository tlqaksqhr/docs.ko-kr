---
title: "방법: Visual Basic에서 사용자 설정 변경"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- user settings [Visual Basic], changing in Visual Basic
- user settings
- My.Settings object [Visual Basic], changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: db35a5d63938fcc508c23af5588957d8dc518676
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-user-settings-in-visual-basic"></a>방법: Visual Basic에서 사용자 설정 변경
설정의 `My.Settings` 개체에 대한 속성에 새 값을 할당하여 사용자 설정을 변경할 수 있습니다.  
  
 `My.Settings` 개체는 각 설정을 속성으로 표시합니다. 속성 이름은 설정 이름과 같고 속성 형식은 설정 형식과 같습니다. 설정의 **범위**는 속성이 읽기 전용인지 여부를 결정합니다. **응용 프로그램** 범위 설정의 속성은 읽기 전용이지만 **사용자** 범위 설정의 속성은 읽기-쓰기입니다. 자세한 내용은 [My.Settings 개체](../../../../visual-basic/language-reference/objects/my-settings-object.md)를 참조하세요.  
  
> [!NOTE]
>  런타임에 사용자 범위의 값을 변경하고 저장할 수 있지만 응용 프로그램 범위 설정은 읽기 전용이고 프로그래밍 방식으로 변경할 수 없습니다. **프로젝트 디자이너**를 사용하거나 응용 프로그램의 구성 파일을 편집하여 응용 프로그램을 만들 때 응용 프로그램 범위 설정을 변경할 수 있습니다. 자세한 내용은 [응용 프로그램 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.  
  
## <a name="example"></a>예제  
 이 예제에서는 `Nickname` 사용자 설정의 값을 변경합니다.  
  
 [!code-vb[VbVbalrMyResources#7](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-change-user-settings_1.vb)]  
  
 이 예제가 작동하려면 응용 프로그램에 `String` 형식의 `Nickname` 사용자 설정이 있어야 합니다.  
  
 응용 프로그램이 종료될 때 사용자 설정이 저장됩니다. 설정을 즉시 저장하려면 `My.Settings.Save` 메서드를 호출합니다. 자세한 내용은 [방법: Visual Basic에서 사용자 설정 유지](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [My.Settings 개체](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [방법: Visual Basic에서 응용 프로그램 설정 읽기](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [방법: Visual Basic에서 사용자 설정 유지](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [방법: Visual Basic에서 사용자 설정의 속성 표 만들기](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [응용 프로그램 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)

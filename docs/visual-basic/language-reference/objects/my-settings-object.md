---
title: My.Settings 개체
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 54176ae6706311b17227c7dc21a5060c9b369753
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mysettings-object"></a>My.Settings 개체
응용 프로그램의 설정에 액세스 하기 위한 메서드와 속성을 제공 합니다.  
  
## <a name="remarks"></a>설명  
 `My.Settings` 개체 응용 프로그램의 설정에 대 한 액세스를 제공 하 고 동적으로 저장 하 고 속성 설정 및 응용 프로그램에 대 한 기타 정보를 검색할 수 있습니다. 자세한 내용은 [응용 프로그램 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.  
  
## <a name="properties"></a>속성  
 `My.Settings` 개체의 속성을 통해 응용 프로그램 설정에 액세스할 수 있습니다. 를 추가 하거나 설정을 제거는 **설정 디자이너**합니다.  
  
 각 설정에는 **이름**, **형식**, **범위**, 및 **값**, 이러한 설정에 따라 결정 하 고 어떻게 각 설정에 액세스 하는 속성 에 표시 된 `My.Settings` 개체:  
  
-   **이름** 속성의 이름을 결정 합니다.  
  
-   **형식** 속성의 유형을 결정 합니다.  
  
-   **범위** 읽기 전용 속성 인지 여부를 나타냅니다. 값이 **응용 프로그램**, 읽기 전용 이면 값이 속성은 **사용자**, 속성은 읽기 / 쓰기입니다.  
  
-   **값** 속성의 기본값입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|---|---|  
|`Reload`|마지막으로 저장 된 값의 사용자 설정을 다시 로드합니다.|  
|`Save`|현재 사용자 설정을 저장합니다.|  
  
 `My.Settings` 개체도 고급 속성과에서 상속 된 메서드를 제공는 <xref:System.Configuration.ApplicationSettingsBase> 클래스입니다.  
  
## <a name="tasks"></a>작업  
 다음 표에서 관련 된 작업의 예를 보여 줍니다.는 `My.Settings` 개체입니다.  
  
|대상|보기|  
|---|---|  
|응용 프로그램 설정 읽기|[방법: Visual Basic에서 응용 프로그램 설정 읽기](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|사용자 설정을 변경|[방법: Visual Basic에서 사용자 설정 변경](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|사용자 설정 유지|[방법: Visual Basic에서 사용자 설정 유지](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|사용자 설정에 대 한 속성 표 만들기|[방법: Visual Basic에서 사용자 설정의 속성 표 만들기](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>예제  
 이 예제에서는 `Nickname` 설정의 값을 표시합니다.  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 이 예제가 작동하려면 응용 프로그램에 `String` 형식의 `Nickname` 설정이 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Configuration.ApplicationSettingsBase>  
 [방법: Visual Basic에서 응용 프로그램 설정 읽기](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [방법: Visual Basic에서 사용자 설정 변경](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [방법: Visual Basic에서 사용자 설정 유지](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [방법: Visual Basic에서 사용자 설정의 속성 표 만들기](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [응용 프로그램 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)

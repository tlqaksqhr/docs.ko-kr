---
title: '방법: C#에서 응용 프로그램에 다중 설정 집합 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 029dffc878c62613e291620a2bd86971f369d15a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>방법: C#에서 응용 프로그램에 다중 설정 집합 추가 #
경우에 따라 응용 프로그램에 여러 집합의 설정 사용 하도록는 것이 좋습니다. 예를 들어을 개발 하는 응용 프로그램 설정의 특정 그룹 자주 변경 하려면 필요한 경우 수도 있습니다 파일 전체적으로 바뀔 수 수 있도록 단일 파일에 모두 구분할 수 다른 설정은 영향을 주지 않습니다 유지. Visual Studio를 사용 하면 여러 설정 집합을 프로젝트에 추가할 수 있습니다. 설정의 추가 집합 Properties.Settings 개체를 통해 액세스할 수 있습니다.  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a>응용 프로그램에 설정 집합을 추가 하려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다. **새 항목 추가** 대화 상자가 열립니다.  
  
2.  에 **새 항목 추가** 대화 상자에서 **설정 파일**파일 이름에 입력 하 고 **추가** 솔루션에 새 설정 파일을 추가 하려면.  
  
3.  **솔루션 탐색기**, 새 설정 파일을 끌어는 **속성** 폴더입니다. 이렇게 하면 새 설정을 코드에서 사용할 수 있도록 합니다.  
  
4.  추가 하 고 다른 설정 파일 설정을이 파일에 사용 합니다. 이 설정 그룹을 Properties.Settings 개체를 통해 액세스할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 설정 및 사용자 설정 사용](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [응용 프로그램 설정 개요](../../../../docs/framework/winforms/advanced/application-settings-overview.md)

---
title: '방법: 응용 프로그램 세션 간 설정 값 변경'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 383f72f223fb92170d16a9538c94e67825009abb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>방법: 응용 프로그램 세션 간 설정 값 변경
때때로 다음 응용 프로그램을 컴파일 및 배포 후 응용 프로그램 세션 간 설정 값을 변경 하는 것이 좋습니다. 예를 들어 다음 올바른 데이터베이스 위치를 가리키도록 연결 문자열을 변경 하는 것이 좋습니다. 이후 응용 프로그램을 컴파일 및 배포 후 디자인 타임 도구를 사용할 수 없는 경우 파일에서 수동으로 설정 값을 변경 해야 합니다.  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>응용 프로그램 세션 간 설정 값을 변경 하려면  
  
1.  Microsoft 메모장 또는 다른 텍스트 또는 XML 편집기를 사용 하 여, 응용 프로그램과 연결 된.config 파일을 엽니다.  
  
2.  변경할 설정에 대 한 항목을 찾습니다. 아래 제시 된 예와 비슷해야 합니다.  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  설정에 대 한 새 값을 입력 하 고 파일을 저장 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 설정 및 사용자 설정 사용](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [응용 프로그램 설정 개요](../../../../docs/framework/winforms/advanced/application-settings-overview.md)

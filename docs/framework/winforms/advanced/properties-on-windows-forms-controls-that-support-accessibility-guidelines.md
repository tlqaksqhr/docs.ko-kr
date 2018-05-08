---
title: 내게 필요한 옵션 지침을 지원하는 Windows Forms 컨트롤의 속성
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: b466dcf42561d8ced7b224215538a807c94b174b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>내게 필요한 옵션 지침을 지원하는 Windows Forms 컨트롤의 속성
표준 Windows Forms 도구 상자에서 컨트롤에 키보드 포커스 노출을 노출 및 화면 요소를 포함 하 여 내게 필요한 옵션 지침을 여러 지원 합니다.  
  
## <a name="planning-ahead-for-accessibility"></a>내게 필요한 옵션에 대 한 미리 계획  
 컨트롤의 속성은 다음 표에 나와 있는 것 처럼 다른 내게 필요한 옵션 지침을 지 원하는 데 사용할 수 있습니다. 또한 메뉴를 사용 하면 프로그램 기능에 대 한 액세스를 제공 해야 합니다.  
  
|컨트롤 속성|내게 필요한 옵션에 대 한 고려 사항|  
|----------------------|--------------------------------------|  
|AccessibleDescription|화면 판독기와 같은 접근성 보조 기능에 대 한 설명을 보고 됩니다. 접근성 보조 기능은 장애가 있는 사용자가 컴퓨터를 보다 효율적으로 사용하도록 돕는 특수 프로그램 및 장치입니다.|  
|AccessibleName|접근성 보조 기능에 보고 되는 이름입니다.|  
|AccessibleRole|사용자 인터페이스에서 해당 요소의 용도 설명합니다.|  
|TabIndex|폼을 탐색할 수 있는 탐색 경로 만듭니다. 연결 된 레이블을 바로 앞에 두 탭 순서에서 해당 텍스트 상자와 같은 내장 레이블이 없는 컨트롤에 대 한 것이 유용 합니다.|  
|텍스트|선택 키를 만들려면 "&" 문자를 사용 합니다. 선택 키를 사용 하 여 기능에 대 한 문서화 된 키보드 액세스를 제공 하는 중입니다.|  
|글꼴 크기|글꼴 크기를 조정할 수 없는 경우 다음 설정 해야 10 포인트 이상으로 합니다. 폼의 글꼴 크기 설정 되 고 나면 이후에 폼에 추가 된 모든 컨트롤 같은 크기를 갖습니다.|  
|Forecolor|이 속성을 기본값으로 설정 된 사용자의 색 기본 설정은 폼에 사용 됩니다.|  
|Backcolor|이 속성을 기본값으로 설정 된 사용자의 색 기본 설정은 폼에 사용 됩니다.|  
|BackgroundImage|이 속성 텍스트를 더 쉽게 읽을 수 있도록 비워 둡니다.|  
  
## <a name="see-also"></a>참고 항목  
 [연습: 내게 필요한 옵션이 지원되는 Windows 기반 응용 프로그램 만들기](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)

---
title: "연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 08cb39215ea1d9aff1cd7ecc125bd731f14a4d7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a>연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기
사용 중인 구성 요소는 현재 열려 있는 솔루션의 프로젝트에서 정의 된 경우 자동으로에 표시 됩니다는 **도구 상자**, 작업이 사용자가 필요 하지 않습니다. 수동으로 채울 수 있습니다는 **도구 상자** 를 사용 하 여 사용자 지정 구성 요소와는 [선택 도구 상자 항목 대화 상자 (Visual Studio)](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb), 하지만 **도구 상자** 고려 솔루션에 있는 항목의 다음 특성을 모두의 출력을 빌드:  
  
-   구현 <xref:System.ComponentModel.IComponent>;  
  
-   없는 <xref:System.ComponentModel.ToolboxItemAttribute> 로 설정 `false`;  
  
-   없는 <xref:System.ComponentModel.DesignTimeVisibleAttribute> 로 설정 `false`합니다.  
  
> [!NOTE]
>  **도구 상자** 때문에 프로젝트 솔루션에 의해 빌드되지 않은 항목을 표시 하지 것입니다 참조 체인을 따르지 않습니다.  
  
 이 연습에서는 사용자 지정 구성 요소에 자동으로 표시 방법을 **도구 상자** 빌드될 때 구성 요소입니다. 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   Windows Forms 프로젝트를 만드는 중입니다.  
  
-   사용자 지정 구성 요소를 만듭니다.  
  
-   사용자 지정 구성 요소의 인스턴스를 만듭니다.  
  
-   언로드 및 사용자 지정 구성 요소를 다시 로드 합니다.  
  
 완료 했으면 확인 하 게는 **도구 상자** 사용자가 만든 구성 요소와 채워집니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  `ToolboxExample`이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다.  
  
     자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)을 참조하세요.  
  
2.  프로젝트에 새 구성 요소를 추가 합니다. 호출 `DemoComponent`합니다.  
  
     자세한 내용은 참조 [NIB: 방법: 새 프로젝트 항목 추가](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)합니다.  
  
3.  프로젝트를 빌드합니다.  
  
4.  **도구** 메뉴를 클릭 하 여는 **옵션** 항목입니다. 클릭 **일반** 아래는 **Windows Forms 디자이너** 항목을 확인 하는 **AutoToolboxPopulate** 옵션이로 설정 되어 **True**합니다.  
  
## <a name="creating-an-instance-of-a-custom-component"></a>사용자 지정 구성 요소 인스턴스 만들기  
 다음 단계는 양식에서 사용자 지정 구성 요소의 인스턴스를 만드는 것입니다. 때문에 **도구 상자** 자동으로 새 구성 요소에 대 한 계정을,이 다른 구성 요소 또는 컨트롤을 만드는 것도 그만큼 용이 합니다.  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a>사용자 지정 구성 요소의 인스턴스를 만들려면  
  
1.  프로젝트의 폼에서 열고는 **Forms 디자이너**합니다.  
  
2.  에 **도구 상자**, 새 탭을 누릅니다 **ToolboxExample 구성 요소**합니다.  
  
     이 탭을 클릭 하면 표시 됩니다 **DemoComponent**합니다.  
  
    > [!NOTE]
    >  성능상의 이유로 구성 요소 자동으로 채워진 영역에는 **도구 상자** 사용자 지정 비트맵을 표시 하지 않습니다 및 <xref:System.Drawing.ToolboxBitmapAttribute> 지원 되지 않습니다. 사용자 지정 구성 요소에 대 한 아이콘을 표시 하려면는 **도구 상자**를 사용 하 여는 **도구 상자 항목 선택** 요소를 로드 하려면 대화 상자.  
  
3.  구성 요소를 폼으로 끕니다.  
  
     구성 요소의 인스턴스 만들어지고에 추가 된 **구성 요소 트레이**합니다.  
  
## <a name="unloading-and-reloading-a-custom-component"></a>언로드 및 사용자 지정 구성 요소를 다시 로드  
 **도구 상자** 고려 각 구성 요소 프로젝트를 로드 하 고 프로젝트를 로드할 프로젝트의 구성 요소에 대 한 참조를 제거 합니다.  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a>언로드 및 구성 요소를 다시 로드의 도구 상자에 영향을 테스트 하려면  
  
1.  솔루션에서 프로젝트를 언로드하십시오.  
  
     프로젝트를 언로드하여에 대 한 자세한 내용은 참조 [NIB: 방법: 프로젝트 다시 로드 및 언로드](http://msdn.microsoft.com/en-us/abc0155b-8fcb-4ffc-95b6-698518a7100b)합니다. 저장 하는 메시지가 선택 **예**합니다.  
  
2.  새로 추가 **Windows 응용 프로그램** 프로젝트를 솔루션입니다. 양식을 엽니다는 **디자이너**합니다.  
  
     **ToolboxExample 구성 요소** 탭에서 이전 프로젝트는 이제 사라집니다.  
  
3.  다시 로드는 `ToolboxExample` 프로젝트.  
  
     **ToolboxExample 구성 요소** 탭 이제 다시 나타납니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습에서는 하는 **도구 상자** 프로젝트의 구성 요소를 고려 되지만 **도구 상자** 컨트롤의 고려 합니다. 추가 하 고 솔루션에서 제어 프로젝트를 제거 하 여 사용자 지정 컨트롤을 시험해 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [옵션 대화 상자, Windows Forms 디자이너, 일반](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834)  
 [방법: 도구 상자 탭 조작](http://msdn.microsoft.com/en-us/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [도구 상자 항목 선택 대화 상자(Visual Studio)](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [Windows Forms에 컨트롤 넣기](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)

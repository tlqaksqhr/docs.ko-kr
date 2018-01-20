---
title: "방법: UserControl의 런타임 동작 테스트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48b7c47a14f27439c60280a5c4202e9f4af76397
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>방법: UserControl의 런타임 동작 테스트
개발 하는 경우는 <xref:System.Windows.Forms.UserControl>, 런타임 동작을 테스트 해야 합니다. 별도 Windows 기반 응용 프로그램 프로젝트를 만들고 테스트 폼에 컨트롤을 배치할 수 있지만이 절차는 불편 합니다. 빠르고 간편 하 게 사용 하는 것은 **UserControl Test Container** Visual Studio에서 제공 합니다. 이 테스트 컨테이너는 Windows 컨트롤 라이브러리 프로젝트에서 직접 시작합니다.  
  
> [!IMPORTANT]
>  로드 테스트 컨테이너에 대 한 프로그램 <xref:System.Windows.Forms.UserControl>, 컨트롤에는 하나 이상의 공용 생성자가 있어야 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
> [!NOTE]
>  Visual c + + 컨트롤을 사용 하 여 테스트할 수 없습니다는 **UserControl Test Container**합니다.  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a>UserControl의 런타임 동작을 테스트 하려면  
  
1.  호출 하는 Windows 컨트롤 라이브러리 프로젝트를 만들 **컨트롤**합니다. 자세한 내용은 참조 [Windows 컨트롤 라이브러리 템플릿](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4)합니다.  
  
2.  에 **Windows Forms 디자이너**를 끌어 한 <xref:System.Windows.Forms.Label> 에서 제어는 **도구 상자** 컨트롤의 디자인 화면으로 합니다.  
  
3.  F5 키를 눌러 프로젝트를 빌드 및 실행 하는 **UserControl Test Container**합니다. 테스트 컨테이너를 표시 하면 <xref:System.Windows.Forms.UserControl> 에 **미리 보기** 창.  
  
4.  선택 된 <xref:System.Windows.Forms.Control.BackColor%2A> 에 표시 된 속성의 <xref:System.Windows.Forms.PropertyGrid> 컨트롤의 오른쪽에는 **미리 보기** 창. 해당 값을 변경할 `ControlDark`합니다. 컨트롤을 더 어두운 색으로 변경 되는지 관찰 합니다. 다른 속성 값을 변경해 보십시오 하 고 컨트롤에 대 한 영향을 관찰 합니다.  
  
5.  클릭는 **사용자 정의 컨트롤 전체 도킹** 아래 확인란의 **미리 보기** 창. 컨트롤의 창에 맞게 크기가 조정 됩니다 있는지 관찰 합니다. 테스트 컨테이너 크기를 조정 하 고 창를 조절 관찰 합니다.  
  
6.  테스트 컨테이너를 닫습니다.  
  
7.  다른 사용자 정의 컨트롤을 추가 **컨트롤** 프로젝트. 자세한 내용은 참조 [NIB: 방법: 프로젝트에 기존 항목 추가](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)합니다.  
  
8.  에 **Windows Forms 디자이너**를 끌어 한 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 컨트롤의 디자인 화면으로 합니다.  
  
9. F5 키를 눌러 프로젝트를 작성 하 고 테스트 컨테이너를 실행 합니다.  
  
10. 클릭는 **사용자 정의 컨트롤 선택** <xref:System.Windows.Forms.ComboBox> 두 개의 사용자 정의 컨트롤 사이 전환 하려면.  
  
## <a name="testing-user-controls-from-another-project"></a>다른 프로젝트에서 사용자 정의 컨트롤 테스트  
 현재 프로젝트의 테스트 컨테이너의 다른 프로젝트의 사용자 정의 컨트롤을 테스트할 수 있습니다.  
  
#### <a name="to-test-user-controls-from-another-project"></a>다른 프로젝트에서 사용자 컨트롤을 테스트 하려면  
  
1.  호출 하는 Windows 컨트롤 라이브러리 프로젝트를 만들 **TestContainerExample2**합니다. 자세한 내용은 참조 [Windows 컨트롤 라이브러리 템플릿](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4)합니다.  
  
2.  에 **Windows Forms 디자이너**를 끌어 한 <xref:System.Windows.Forms.RadioButton> 에서 제어는 **도구 상자** 컨트롤의 디자인 화면으로 합니다.  
  
3.  F5 키를 눌러 프로젝트를 작성 하 고 테스트 컨테이너를 실행 합니다. 테스트 컨테이너를 표시 하면 <xref:System.Windows.Forms.UserControl> 에 **미리 보기** 창.  
  
4.  클릭는 **부하** 단추입니다.  
  
5.  에 **열려** 대화 상자에서로 이동 **컨트롤**이전 절차에서 빌드한.dll입니다. 선택 **컨트롤**.dll 및 클릭은 **열려** 사용자 정의 컨트롤을 로드 하는 단추  
  
6.  사용 하 여는 **사용자 정의 컨트롤 선택** <xref:System.Windows.Forms.ComboBox> 에서 두 개의 사용자 정의 컨트롤 사이 전환 하려면는 **컨트롤** 프로젝트.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.UserControl>  
 [방법: 복합 컨트롤 작성](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [연습: Visual Basic에서 합성 컨트롤 작성](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [연습: Visual C#에서 합성 컨트롤 작성](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [사용자 정의 컨트롤 디자이너가](http://msdn.microsoft.com/library/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)

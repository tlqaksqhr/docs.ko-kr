---
title: "방법: Windows Forms에 ActiveX 컨트롤 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: afee07f2f5009abb6cf8facc94b138f4ea2a11fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>방법: Windows Forms에 ActiveX 컨트롤 추가
Windows Forms 컨트롤 호스트에 Windows Forms 디자이너가 최적화 하는 동안에 Windows Forms에서 ActiveX 컨트롤을 넣을 수 있습니다.  
  
> [!CAUTION]
>  ActiveX 컨트롤에 추가 되는 경우 Windows Forms에 대 한 성능 제한이 있습니다.  
  
 ActiveX 컨트롤을 폼에 추가 하기 전에 도구 상자에 추가 해야. 자세한 내용은 참조 [COM 구성 요소, 사용자 지정 도구 상자 대화 상자](http://msdn.microsoft.com/en-us/171333f3-f207-4e02-bbdc-17862556212c)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 클릭합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>ActiveX 컨트롤을 Windows Form을 추가 하려면  
  
-   도구 상자에 컨트롤을 두 번 클릭 합니다.  
  
     [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]컨트롤에 대 한 모든 참조는 프로젝트에에서 추가 합니다. Windows Forms에서 ActiveX 컨트롤을 사용 하는 경우 유의 해야 할 사항에 대 한 자세한 내용은 참조 [Windows Form에서 ActiveX 컨트롤을 호스팅할 때의 고려 사항](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md)합니다.  
  
    > [!NOTE]
    >  Windows Forms ActiveX 컨트롤 가져오기 (AxImp.exe) ActiveX 동적 연결 라이브러리를 가져오는에 예상 보다 다른 종류의 이벤트 인수를 만듭니다. AxImp.exe에서 만든 인수는 다음과 같은: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`때 `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` 가 필요 합니다. 주의이 불일치로 하지 않는 코드는 정상적으로 작동 합니다. 자세한 내용은 참조 [Windows Forms ActiveX 컨트롤 가져오기 (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)  
 [여러 언어 및 라이브러리에서 사용되는 컨트롤 및 프로그래밍 가능한 개체 비교](http://msdn.microsoft.com/en-us/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)

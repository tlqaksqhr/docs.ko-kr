---
title: '방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시'
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: 7e452c3d3be131b891ee26555e3085fc31b04517
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시
개발 하 고 컨트롤을 배포 하면 이러한 컨트롤에 표시 되도록 할 수 있습니다는 **도구 상자 항목 선택** 마우스 오른쪽 단추로 클릭할 때 표시 되는 대화 상자는 **도구 상자** 선택  **항목 선택**합니다. AssemblyFoldersEx 등록 절차를 사용 하 여이 대화 상자에 표시할 컨트롤을 설정할 수 있습니다.  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a>도구 상자 항목 선택 대화 상자에서 컨트롤을 표시 하려면  
  
-   컨트롤 어셈블리를 전역 어셈블리 캐시에 설치 합니다. 자세한 내용은 참조 [하는 방법: 전역 어셈블리 캐시에 어셈블리 설치](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
  
     -또는-  
  
-   AssemblyFoldersEx 등록 절차를 사용 하 여 컨트롤 및 해당 연결 된 디자인 타임 어셈블리를 등록 합니다. AssemblyFoldersEx 공급 업체 원하는 프레임 워크의 각 버전에 대 한 경로 저장 하는 레지스트리 위치는입니다. 참조 어셈블리를 찾는이 레지스트리 위치에 디자인 타임 확인 합니다. 레지스트리 스크립트를 도구 상자에 표시할 컨트롤을 지정할 수 있습니다. 자세한 내용은 참조 [컨트롤 사용자 지정 및 디자인 타임 어셈블리 (Visual Studio 2013) 배포](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [도구 상자 항목 선택 대화 상자(Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [사용자 지정 컨트롤 및 디자인 타임 어셈블리 (Visual Studio 2013) 배포](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [디자인 타임에 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [방법: 전역 어셈블리 캐시에 어셈블리 설치](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)

---
title: Power Packs 컨트롤 (Visual Studio)를 참조 하는 응용 프로그램 배포
ms.date: 07/20/2015
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
ms.openlocfilehash: bd235bc0b4a7f9978333931ae1dce012c0950374
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39198230"
---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a>Power Packs 컨트롤 (Visual Studio)를 참조 하는 응용 프로그램 배포
Power Packs 컨트롤을 참조 하는 응용 프로그램을 배포 하려는 경우 (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>를 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, 또는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), 대상 컴퓨터의 컨트롤을 설치 해야 합니다.  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a>Power Packs 컨트롤의 필수 구성 요소로 설치  
 응용 프로그램을 성공적으로 배포하려면 응용 프로그램이 참조하는 모든 구성 요소도 배포해야 합니다. 필수 조건 구성 요소를 설치하는 프로세스를 *부트스트래핑*이라고 합니다.  
  
 Visual Studio는 개발 컴퓨터에 설치 하는 경우 Power Packs 부트스트래퍼 패키지가 Visual Studio 부트스트래퍼 디렉터리에 추가 됩니다. 이 패키지는 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 또는 Windows Installer 배포에 대한 필수 조건을 추가하는 절차를 수행할 때 사용할 수 있습니다.  
  
 기본적으로 부트스트랩된 구성 요소는 설치 패키지와 같은 위치에서 배포됩니다. 또는 사용자가 필요한 경우 다운로드할 수 있는 URL 또는 파일 공유 위치에서 구성 요소를 배포하도록 선택할 수 있습니다.  
  
> [!NOTE]
>  부트스트랩된 구성 요소를 설치하려면 사용자는 컴퓨터에서 관리 권한이나 비슷한 사용자 권한이 필요할 수 있습니다. [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 응용 프로그램의 경우 이는 응용 프로그램에서 지정된 보안 수준과 관계없이 응용 프로그램을 설치할 관리 권한이 사용자에게 필요함을 의미합니다. 응용 프로그램이 설치되고 나면 사용자는 관리 권한 없이 응용 프로그램을 실행할 수 있습니다.  
  
 설치 하는 동안 사용자 대상 컴퓨터에 없는 경우 Power Packs 컨트롤을 설치 하 라는 메시지가 됩니다.  
  
 부트스트래핑 대신 Microsoft Systems Management Server와 같은 전자적 소프트웨어 배포 시스템을 사용 하 여 Power Packs 컨트롤을 미리 배포할 수 있습니다.  
  
## <a name="see-also"></a>참고자료  
 [방법: ClickOnce 응용 프로그램을 사용하여 필수 조건 설치](/visualstudio/deployment/how-to-install-prerequisites-with-a-clickonce-application)  
 [Visual Basic Power Packs 컨트롤](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)

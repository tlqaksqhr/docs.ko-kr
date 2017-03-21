---
title: "Power Packs 컨트롤 (Visual Studio)를 참조 하는 응용 프로그램 배포 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Power Packs, deploying
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4d342e655dcfe18ed3b5fc1d2710571ed8e3369e
ms.lasthandoff: 03/13/2017

---
# <a name="deploying-applications-that-reference-power-packs-controls-visual-studio"></a>Power Packs 컨트롤 (Visual Studio)를 참조 하는 응용 프로그램 배포
Power Packs 컨트롤을 참조 하는 응용 프로그램을 배포 하려는 경우 (<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>, 또는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>), 대상 컴퓨터에 컨트롤을 설치 해야 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> </xref:Microsoft.VisualBasic.PowerPacks.OvalShape> </xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
  
## <a name="installing-the-power-packs-controls-as-a-prerequisite"></a>Power Packs 컨트롤의 필수 구성 요소 설치  
 응용 프로그램을 성공적으로 배포하려면 응용 프로그램이 참조하는 모든 구성 요소도 배포해야 합니다. 필수 조건 구성 요소를 설치하는 프로세스를 *부트스트래핑*이라고 합니다.  
  
 때 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 부트스트래퍼 패키지에 추가 되는 파워 팩 개발 컴퓨터에 설치 된 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 부트스트래퍼 디렉터리입니다. 에 대 한 필수 구성 요소를 추가 하기 위한 절차를 수행 하는 경우에이 패키지는 사용할 수 있는 다음 [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] 또는 Windows Installer 배포 합니다.  
  
 기본적으로 부트스트랩된 구성 요소는 설치 패키지와 같은 위치에서 배포됩니다. 또는 사용자가 필요한 경우 다운로드할 수 있는 URL 또는 파일 공유 위치에서 구성 요소를 배포하도록 선택할 수 있습니다.  
  
> [!NOTE]
>  부트스트랩된 구성 요소를 설치하려면 사용자는 컴퓨터에서 관리 권한이나 비슷한 사용자 권한이 필요할 수 있습니다. 에 대 한 [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] 응용 프로그램, 즉, 응용 프로그램에 의해 지정 된 보안 수준에 관계 없이 응용 프로그램을 설치 하려면 관리자 권한이 필요할 수 있습니다. 응용 프로그램이 설치되고 나면 사용자는 관리 권한 없이 응용 프로그램을 실행할 수 있습니다.  
  
 설치 하는 동안 사용자가 대상 컴퓨터에 존재 하지 않는 경우 Power Packs 컨트롤을 설치 하 라는 메시지가 됩니다.  
  
 부트스트래핑을 수행 하는 대신, Microsoft Systems Management Server와 같은 전자 소프트웨어 배포 시스템을 사용 하 여 Power Packs 컨트롤을 미리 배포할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: ClickOnce 응용 프로그램 필수 구성 요소 설치](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5)   
 [Visual Basic Power Packs 컨트롤](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)

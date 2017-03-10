---
title: "Deploying Applications That Reference Power Packs Controls (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Power Packs, deploying"
ms.assetid: f2230f53-a745-4731-89e6-033943faa209
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Deploying Applications That Reference Power Packs Controls (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Power Packs 컨트롤\(<xref:Microsoft.VisualBasic.PowerPacks.LineShape>, <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>, <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 또는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\)을 참조하는 응용 프로그램을 배포하려면 대상 컴퓨터에 컨트롤이 설치되어 있어야 합니다.  
  
## 필수 구성 요소로 Power Packs 컨트롤 설치  
 응용 프로그램을 성공적으로 배포하려면 응용 프로그램에서 참조하는 모든 구성 요소를 함께 배포해야 합니다.  필수 구성 요소를 설치하는 과정을 *부트스트래핑*이라고 합니다.  
  
 개발 컴퓨터에 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]가 설치하면 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] bootstrapper 디렉터리에 Power Packs 부트스트래퍼 패키지가 추가됩니다.  그러면 [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)] 또는 Windows Installer 배포를 위한 필수 구성 요소를 추가할 때 이 패키지를 사용할 수 있습니다.  
  
 기본적으로 부트스트랩된 구성 요소는 설치 패키지와 동일한 위치에서 배포됩니다.  사용자가 필요에 따라 구성 요소를 다운로드할 수 있는 URL 또는 파일 공유 위치에서 구성 요소를 배포하도록 선택할 수도 있습니다.  
  
> [!NOTE]
>  부트스트랩된 구성 요소를 설치하려면 컴퓨터에 대해 관리자 권한이나 이와 유사한 사용자 권한이 필요할 수 있습니다.  [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick-md.md)] 응용 프로그램의 경우에는 응용 프로그램에서 지정한 보안 수준에 관계없이 응용 프로그램을 설치하는 데 관리자 권한이 필요할 수 있습니다.  응용 프로그램이 설치된 후에는 사용자가 관리자 권한 없이 응용 프로그램을 실행할 수 있습니다.  
  
 설치할 때 대상 컴퓨터에 Power Packs 컨트롤이 없으면 해당 컨트롤을 설치하라는 메시지가 표시됩니다.  
  
 부트스트래핑을 사용하는 대신 Microsoft Systems Management Server와 같은 전자 소프트웨어 배포 시스템을 사용하여 Power Packs 컨트롤을 사전 배포할 수 있습니다.  
  
## 참고 항목  
 [How to: Install Prerequisites in Windows Installer Deployment](http://msdn.microsoft.com/ko-kr/653fc868-2486-429c-b75e-2f9d0c7f6619)   
 [방법: ClickOnce 응용 프로그램을 사용하여 필수 구성 요소 설치](../Topic/How%20to:%20Install%20Prerequisites%20with%20a%20ClickOnce%20Application.md)   
 [Not in Build: Choosing a Deployment Strategy](http://msdn.microsoft.com/ko-kr/ecd632d8-063c-4028-b785-81bba045107b)   
 [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)
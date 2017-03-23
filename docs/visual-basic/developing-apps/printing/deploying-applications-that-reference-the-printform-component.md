---
title: "PrintForm 구성 요소 (Visual Basic)를 참조 하는 응용 프로그램 배포 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- PrintForm component [Visual Basic], deploying
ms.assetid: b595ea44-a712-4625-a761-190c64f59bbe
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 016643329d2ee66ca5a32f155cf91e0ee137f38f
ms.lasthandoff: 03/13/2017

---
# <a name="deploying-applications-that-reference-the-printform-component-visual-basic"></a>PrintForm 구성 요소 (Visual Basic)를 참조 하는 응용 프로그램 배포
참조 하는 응용 프로그램을 배포 하려는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>구성 요소를 대상 컴퓨터에 구성 요소를 설치 해야 합니다.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 PowerPack 컨트롤은 Visual Studio에 더 포함되지 않지만 [다운로드 센터](http://www.microsoft.com/en-us/download/details.aspx?id=25169)에서 다운로드할 수 있습니다.  
  
## <a name="installing-the-printform-as-a-prerequisite"></a>필수 구성 요소로 PrintForm 설치  
 응용 프로그램을 성공적으로 배포하려면 응용 프로그램이 참조하는 모든 구성 요소도 배포해야 합니다. 필수 조건 구성 요소를 설치하는 프로세스를 *부트스트래핑*이라고 합니다.  
  
 경우는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>개발 컴퓨터에 구성 요소가 설치 되어, Microsoft Visual Basic Power Packs 부트스트래퍼 패키지에 추가 되는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 부트스트래퍼 디렉터리.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 에 대 한 필수 구성 요소를 추가 하기 위한 절차를 수행 하는 경우에이 패키지는 사용할 수 있는 다음 [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] 또는 Windows Installer 배포 합니다.  
  
 기본적으로 부트스트랩된 구성 요소는 설치 패키지와 같은 위치에서 배포됩니다. 또는 사용자가 필요한 경우 다운로드할 수 있는 URL 또는 파일 공유 위치에서 구성 요소를 배포하도록 선택할 수 있습니다.  
  
> [!NOTE]
>  부트스트랩된 구성 요소를 설치하려면 사용자는 컴퓨터에서 관리 권한이나 비슷한 사용자 권한이 필요할 수 있습니다. 에 대 한 [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] 응용 프로그램, 즉, 응용 프로그램에 의해 지정 된 보안 수준에 관계 없이 응용 프로그램을 설치 하려면 관리자 권한이 필요할 수 있습니다. 응용 프로그램이 설치되고 나면 사용자는 관리 권한 없이 응용 프로그램을 실행할 수 있습니다.  
  
 설치 하는 동안 메시지가 나타납니다를 설치 하는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>구성 요소는 대상 컴퓨터에 없는 경우.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
 부트스트래핑을 수행 하는 대신, 미리 배포할 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>Microsoft Systems Management Server와 같은 전자 소프트웨어 배포 시스템을 사용 하 여 구성 요소.</xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm>  
  
## <a name="see-also"></a>참고 항목  
 [방법: ClickOnce 응용 프로그램 필수 구성 요소 설치](http://msdn.microsoft.com/library/e964fca5-fdfd-47cf-a1c9-7fb96b1c88b5)   
 [PrintForm 구성 요소](../../../visual-basic/developing-apps/printing/printform-component.md)

---
title: "방법: 어셈블리 로드 및 언로드 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd52a1094dba16c7e1bcba5bface9e13747cd4f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a>방법: 어셈블리 로드 및 언로드 (Visual Basic)
프로그램에서 참조하는 어셈블리는 빌드 시 자동으로 로드되지만, 런타임에 현재 응용 프로그램 도메인에 특정 어셈블리를 로드할 수도 있습니다. 자세한 내용은 [방법: 응용 프로그램 도메인에 어셈블리 로드](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)를 참조하세요.  
  
 해당 어셈블리가 포함된 응용 프로그램 도메인을 모두 언로드하지 않으면 개별 어셈블리를 언로드할 수 없습니다. 어셈블리가 범위를 벗어난 경우에도 실제 어셈블리 파일은 해당 파일을 포함하는 응용 프로그램 도메인이 모두 언로드될 때까지 로드된 상태로 유지됩니다.  
  
 일부 어셈블리만 언로드하고 다른 어셈블리는 언로드하지 않으려는 경우 새 응용 프로그램 도메인을 만들고, 이 도메인 내에서 코드를 실행한 다음 해당 응용 프로그램 도메인을 언로드하는 것이 좋습니다. 자세한 내용은 [방법: 응용 프로그램 도메인 언로드](../../../../framework/app-domains/how-to-unload-an-application-domain.md)를 참조하세요.  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>응용 프로그램 도메인에 어셈블리를 로드하려면  
  
1.  <xref:System.AppDomain> 및 <xref:System.Reflection> 클래스에 포함된 여러 로드 메서드 중 하나를 사용합니다. 자세한 내용은 [방법: 응용 프로그램 도메인에 어셈블리 로드](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)를 참조하세요.  
  
### <a name="to-unload-an-application-domain"></a>응용 프로그램 도메인을 언로드하려면  
  
1.  해당 어셈블리가 포함된 응용 프로그램 도메인을 모두 언로드하지 않으면 개별 어셈블리를 언로드할 수 없습니다. <xref:System.AppDomain>의 `Unload` 메서드를 사용하여 응용 프로그램 도메인을 언로드합니다. 자세한 내용은 [방법: 응용 프로그램 도메인 언로드](../../../../framework/app-domains/how-to-unload-an-application-domain.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)  
 [어셈블리와 전역 어셈블리 캐시(Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [방법: 응용 프로그램 도메인에 어셈블리 로드](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)

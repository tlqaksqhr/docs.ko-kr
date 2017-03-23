---
title: "방법: 어셈블리 로드 및 언로드 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 460d3a18fdee74c9b9c49ee465247b5b12d554d8
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a>방법: 어셈블리 로드 및 언로드 (Visual Basic)
프로그램에서 참조 어셈블리를 빌드 시 자동으로 로드할 수는 있지만 런타임에 현재 응용 프로그램 도메인에 특정 어셈블리를 로드 하도 가능. 자세한 내용은 참조 [하는 방법: 응용 프로그램 도메인에 로드 어셈블리](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)합니다.  
  
 모든 것을 포함 하는 응용 프로그램 도메인을 언로드하지 않고 개별 어셈블리를 언로드할 수 없는 방법이 있습니다. 어셈블리 범위를 벗어나면 하는 경우에를 포함 하는 모든 응용 프로그램 도메인 로드 될 때까지 실제 어셈블리 파일은 로드 된 상태로 유지 됩니다.  
  
 일부 어셈블리 일부만 언로드하려면 하려는 경우 새 응용 프로그램 도메인을 만들고 해당 도메인 내의 코드를 실행 한 다음 해당 응용 프로그램 도메인 언로드 것이 좋습니다. 자세한 내용은 참조 [하는 방법: 응용 프로그램 도메인 언로드](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192)합니다.  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>응용 프로그램 도메인에 어셈블리를 로드 하려면  
  
1.  클래스와 <xref:System.AppDomain>및 <xref:System.Reflection>.</xref:System.Reflection> </xref:System.AppDomain> 에 포함 된 여러 로드 메서드 중 하나를 사용 하 여 자세한 내용은 참조 [하는 방법: 응용 프로그램 도메인에 로드 어셈블리](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)합니다.  
  
### <a name="to-unload-an-application-domain"></a>응용 프로그램 도메인 언로드  
  
1.  모든 것을 포함 하는 응용 프로그램 도메인을 언로드하지 않고 개별 어셈블리를 언로드할 수 없는 방법이 있습니다. 사용 된 `Unload` 메서드에서 <xref:System.AppDomain>응용 프로그램 도메인 언로드.</xref:System.AppDomain> 자세한 내용은 참조 [하는 방법: 응용 프로그램 도메인 언로드](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)   
 [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [방법: 응용 프로그램 도메인에 어셈블리를 로드 합니다.](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)

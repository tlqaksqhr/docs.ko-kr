---
title: "방법: 다른 응용 프로그램 (Visual Basic) 프로그램과 어셈블리 공유 | Microsoft 문서"
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
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8065a66c8f7c7b9ccb9125b060b0c03cde273482
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a>방법: 다른 응용 프로그램 (Visual Basic) 프로그램과 어셈블리 공유
어셈블리 전용 또는 공유 될 수 있습니다: 기본적으로 대부분의 간단한 프로그램으로 구성 전용 어셈블리의 하므로 다른 응용 프로그램에서 사용할 수 없습니다.  
  
 다른 응용 프로그램과 어셈블리를 공유할 수 있도록 배치 해야에 [전역 어셈블리 캐시](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) (GAC)입니다.  
  
### <a name="sharing-an-assembly"></a>어셈블리 공유  
  
1.  어셈블리를 만듭니다. 자세한 내용은 참조 [어셈블리 만들기](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4)합니다.  
  
2.  어셈블리에 강력한 이름을 할당 합니다. 자세한 내용은 참조 [하는 방법: 강력한 이름으로 어셈블리 서명](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67)합니다.  
  
3.  어셈블리에 버전 정보를 할당 합니다. 자세한 내용은 참조 [어셈블리 버전 관리](https://msdn.microsoft.com/library/51ket42z)합니다.  
  
4.  전역 어셈블리 캐시에 어셈블리를 추가 합니다. 자세한 내용은 참조 [하는 방법: 전역 어셈블리 캐시에 어셈블리 설치](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743)합니다.  
  
5.  다른 응용 프로그램에서 어셈블리에 포함 된 형식에 액세스 합니다. 자세한 내용은 참조 [하는 방법: 강력한 이름의 어셈블리를 참조](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)
 [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [어셈블리를 사용한 프로그래밍](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)

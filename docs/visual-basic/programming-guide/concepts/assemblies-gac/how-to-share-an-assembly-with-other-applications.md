---
title: "방법: 다른 응용 프로그램 (Visual Basic) 프로그램과 어셈블리 공유"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c079250211a4216b09e84140ff537b3f57127967
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a>방법: 다른 응용 프로그램 (Visual Basic) 프로그램과 어셈블리 공유
어셈블리는 전용이거나 공유될 수 있습니다. 기본적으로 대부분의 간단한 프로그램은 다른 응용 프로그램에서 사용되지 않으므로 전용 어셈블리로 구성됩니다.  
  
 다른 응용 프로그램과 어셈블리를 공유하려면 GAC([전역 어셈블리 캐시](../../../../framework/app-domains/gac.md))에 배치해야 합니다.  
  
### <a name="sharing-an-assembly"></a>어셈블리 공유  
  
1.  어셈블리를 만듭니다. 자세한 내용은 [어셈블리 만들기](../../../../framework/app-domains/create-assemblies.md)를 참조하세요.  
  
2.  어셈블리에 강력한 이름을 할당합니다. 자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)을 참조하세요.  
  
3.  어셈블리에 버전 정보를 할당합니다. 자세한 내용은 [어셈블리 버전 관리](../../../../framework/app-domains/assembly-versioning.md)를 참조하세요.  
  
4.  전역 어셈블리 캐시에 어셈블리를 추가합니다. 자세한 내용은 [방법: 전역 어셈블리 캐시에 어셈블리 설치](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md)를 참조하세요.  
  
5.  다른 응용 프로그램에서 어셈블리에 포함된 형식에 액세스합니다. 자세한 내용은 [방법: 강력한 이름의 어셈블리 참조](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md) [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [어셈블리를 사용한 프로그래밍](../../../../framework/app-domains/programming-with-assemblies.md)

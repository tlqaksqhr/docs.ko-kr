---
title: "방법: 다른 응용 프로그램과 어셈블리 공유(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 79397b18b67becf91d04358ea62cb2351be7d252
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a>방법: 다른 응용 프로그램과 어셈블리 공유(C#)
어셈블리는 전용이거나 공유될 수 있습니다. 기본적으로 대부분의 간단한 프로그램은 다른 응용 프로그램에서 사용되지 않으므로 전용 어셈블리로 구성됩니다.  
  
 다른 응용 프로그램과 어셈블리를 공유하려면 GAC([전역 어셈블리 캐시](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202))에 배치해야 합니다.  
  
### <a name="sharing-an-assembly"></a>어셈블리 공유  
  
1.  어셈블리를 만듭니다. 자세한 내용은 [어셈블리 만들기](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4)를 참조하세요.  
  
2.  어셈블리에 강력한 이름을 할당합니다. 자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67)을 참조하세요.  
  
3.  어셈블리에 버전 정보를 할당합니다. 자세한 내용은 [어셈블리 버전 관리](https://msdn.microsoft.com/library/51ket42z)를 참조하세요.  
  
4.  전역 어셈블리 캐시에 어셈블리를 추가합니다. 자세한 내용은 [방법: 전역 어셈블리 캐시에 어셈블리 설치](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743)를 참조하세요.  
  
5.  다른 응용 프로그램에서 어셈블리에 포함된 형식에 액세스합니다. 자세한 내용은 [방법: 강력한 이름의 어셈블리 참조](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../../csharp/programming-guide/index.md)   
 [어셈블리를 사용한 프로그래밍](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)

---
title: "방법: 사전을 사용하여 이벤트 인스턴스 저장(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bca140ee4d7519f67d6e896757b3187ac169de1f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>방법: 사전을 사용하여 이벤트 인스턴스 저장(C# 프로그래밍 가이드)
`accessor-declarations`는 각 이벤트에 대한 필드를 할당하지 않고 사전을 통해 이벤트 인스턴스를 저장하여 많은 이벤트를 공개하는 데 사용됩니다. 이 기능은 많은 이벤트가 있지만 대부분의 이벤트가 구현되지 않을 것으로 예상하는 경우에만 유용합니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [이벤트](../../../csharp/programming-guide/events/index.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)


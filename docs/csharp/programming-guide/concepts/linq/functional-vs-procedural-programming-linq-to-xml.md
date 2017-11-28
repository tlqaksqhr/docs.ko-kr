---
title: "함수형 프로그래밍과 절차적 프로그래밍 비교(LINQ to XML)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b6aa8ce45afdb68f7ff544b8c8f2f5e1e4a79533
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a>함수형 프로그래밍과 절차적 프로그래밍 비교(LINQ to XML)(C#)
다양한 유형의 XML 응용 프로그램이 있습니다.  
  
-   일부 응용 프로그램에서는 소스 XML 문서를 사용하여 소스 문서와 모양이 다른 새 XML 문서를 생성합니다.  
  
-   소스 XML 문서를 사용하여 HTML 또는 CSV 텍스트 파일과 같이 완전히 다른 형태의 결과 문서를 생성하는 응용 프로그램도 있습니다.  
  
-   어떤 응용 프로그램에서는 소스 XML 문서를 사용하여 데이터베이스에 레코드를 삽입합니다.  
  
-   데이터베이스 등의 다른 소스에서 데이터를 가져와서 해당 데이터로 XML 문서를 만드는 응용 프로그램도 있습니다.  
  
 이러한 응용 프로그램이 XML 응용 프로그램의 모든 유형은 아니지만 XML 프로그래머가 구현해야 하는 기능 유형의 대표적인 집합을 나타냅니다.  
  
 이러한 유형의 응용 프로그램에는 개발자가 선택할 수 있는 두 가지 대조적인 방법이 있습니다.  
  
-   선언적 방법을 사용하는 함수 생성  
  
-   절차적 코드를 사용하는 메모리 내 XML 트리 수정  
  
 LINQ to XML에서는 두 방법을 모두 지원합니다.  
  
 함수 방법을 사용하는 경우 소스 문서를 사용하여 원하는 모양의 완전히 새로운 결과 문서를 생성하는 변환을 작성합니다.  
  
 메모리 내 XML 트리를 수정하는 경우 메모리 내 XML 트리의 노드를 트래버스하고 탐색하여 필요에 따라 노드를 삽입, 삭제 및 수정하는 코드를 작성합니다.  
  
 두 방법 중 하나로 LINQ to XML을 사용할 수 있습니다. 두 방법은 동일한 클래스를 사용하며 경우에 따라 동일한 메서드를 사용합니다. 그러나 두 방법의 구조와 목표는 매우 다릅니다. 예를 들어 상황에 따라 성능이 높고 메모리를 적게 사용하는 방법이 달라집니다. 또한 유지 관리하기가 더 쉬운 코드를 작성하고 생성하는 것이 용이한 방법도 상황에 따라 다릅니다.  
  
 두 방법을 대조하는 내용을 보려면 [메모리 내 XML 트리 수정과 함수 생성 비교(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)를 참조하세요.  
  
 함수 변환 작성에 대한 자습서는 [XML의 순수 함수 변환(C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML 프로그래밍 개요(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)

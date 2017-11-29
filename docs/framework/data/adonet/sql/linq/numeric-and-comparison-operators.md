---
title: "숫자 및 비교 연산자"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f77cb612468b401f6aa526e46cc7481d0b47d385
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="numeric-and-comparison-operators"></a>숫자 및 비교 연산자
산술 및 비교 연산자는 CLR(공용 언어 런타임) 예외에서 다음과 같이 예상대로 동작합니다.  
  
-   SQL에서는 부동 소수점 숫자에 대해 모듈 연산자를 지원하지 않습니다.  
  
-   SQL에서는 unchecked 산술 연산을 지원하지 않습니다.  
  
-   증가 및 감소 연산자를 SQL에서 복제할 수 없는 식에 사용하면 예기치 않은 결과가 발생할 수 있기 때문에 두 연산자는 지원되지 않습니다.  
  
## <a name="supported-operators"></a>지원되는 연산자  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 다음 연산자를 지원합니다.  
  
-   기본 산술 연산자:  
  
    -   `+`  
  
    -   `-`(빼기)  
  
    -   `*`  
  
    -   `/`  
  
    -   `\`(Visual Basic 정수 나누기)  
  
    -   `%`(Visual Basic `Mod`)  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-`(단항 부정 연산자)  
  
-   기본 비교 연산자:  
  
    -   Visual Basic `=` 및 C# `==`  
  
    -   Visual Basic `<>` 및 C# `!=`  
  
    -   Visual Basic `Is/IsNot`  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식 및 함수](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [C# 연산자](http://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [연산자](../../../../../visual-basic/language-reference/operators/index.md)

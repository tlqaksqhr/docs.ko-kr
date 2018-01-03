---
title: "형식 &#39;의 값 &lt;typename1&gt;&#39; 변환할 수 없습니다 &#39;&lt; typename2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords: BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b583c4272dd6e964de99fb14d2795152c655f3aa
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a>형식 &#39;의 값 &lt;typename1&gt;&#39; 변환할 수 없습니다 &#39;&lt; typename2&gt;&#39;
형식의 값 '\<typename1 >'로 변환할 수 없습니다 '\<typename2 >'입니다. 형식 불일치 어셈블리에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 있기 때문일 수 있습니다 '\<assemblyname >'입니다. 에 대 한 파일 참조를 바꿔 보십시오 '\<파일 경로 >' 프로젝트에서 '\<projectname1 >'에 대 한 프로젝트 참조 '\<projectname2 >'입니다.  
  
 프로젝트 하면 프로젝트 참조와 파일 참조를 모두 상황에서는 컴파일러 유형임을 다른 변환 되어야 함을 보장할 수 없습니다.  
  
 다음 의사 코드에서는이 오류를 생성할 수 있는 상황을 보여 줍니다.  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 프로젝트 `P1` 프로젝트를 통해 간접 프로젝트 참조 `P2` 프로젝트에 `P3`에 대 한 직접 파일 참조도 `P3`합니다. 선언 `commonObject` 에 대 한 파일 참조를 사용 하 여 `P3`, 호출 동안 `P2.getCommonClass` 에 대 한 프로젝트 참조를 사용 하 여 `P3`합니다.  
  
 이 경우 문제 파일 참조의 출력 파일의 이름과 파일 경로 지정 하는 `P3` (일반적으로 p3.dll) 프로젝트 참조 소스 프로젝트를 식별 하는 동안 (`P3`) 프로젝트 이름으로 합니다. 이 때문에 컴파일러 보장할 수 없습니다는 유형을 `P3.commonClass` 두 개의 다른 참조를 통해 동일한 소스 코드에서 제공 합니다.  
  
 이 상황은 일반적으로 발생 경우 프로젝트 참조와 파일 참조가 섞여 있습니다. 앞의 그림에서 문제가 발생 하지 않습니다 `P1` 대 한 직접 프로젝트 참조를 `P3` 파일 참조를 대신 합니다.  
  
 **오류 ID:** BC30955  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   프로젝트 참조에 대 한 파일 참조를 변경 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 형식 변환](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)  
 

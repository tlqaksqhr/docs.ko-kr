---
title: 암시적으로 형식화된 람다 식
description: 암시적 형식 변수 선언을 사용하여 람다 식을 선언할 수 없는 이유를 알아봅니다.
ms.date: 06/20/2016
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
ms.openlocfilehash: f06c55f51c30c941d6d507ac8e2edd95c5152742
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33211825"
---
# <a name="implicitly-typed-lambda-expressions"></a>암시적으로 형식화된 람다 식

이 식 트리를 선언하기 위해 `var`을 사용하지 않습니다. 암시적 형식 변수 선언을 사용하여 람다 식을 선언할 수 없습니다.
컴파일러에 대한 순환 논리 문제를 만듭니다. `var` 선언은 대입 연산자의 오른쪽에 있는 식의 형식에서 변수의 형식을 확인하도록 컴파일러에 지시합니다. 람다 식에는 컴파일 시간 형식이 없지만 일치하는 모든 대리자 또는 식 형식으로 변환할 수 있습니다. 대리자 또는 식 형식의 변수에 람다 식을 할당하는 경우 람다 식을 시도하고 '담당자' 변수의 시그니처와 일치하는 식 또는 대리자로 변환하도록 컴파일러에 지시하는 것입니다. 컴파일러는 할당의 오른쪽 형식을 할당의 왼쪽 형식과 일치시키려고 해야 합니다. 

할당의 양쪽 모두 대입 연산자의 다른 쪽에 있는 개체를 검사하고 형식이 일치하는지 확인하도록 컴파일러에 지시할 수 없습니다.

C# 언어에서 해당 동작을 지정하는 이유에 대한 세부 정보를 확인하려면 [이 문서](http://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf)(PDF 다운로드)를 참조하세요.



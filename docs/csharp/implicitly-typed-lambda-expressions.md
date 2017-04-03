---
title: "암시적으로 형식화된 람다 식"
description: "암시적으로 형식화된 람다 식"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c3621f6feb29929d3681b6ed66cc12c5d8018ba1
ms.lasthandoff: 03/13/2017

---

# <a name="implicitly-typed-lambda-expressions"></a>암시적으로 형식화된 람다 식

이 식 트리를 선언하기 위해 `var`을 사용하지 않습니다. 암시적 형식 변수 선언을 사용하여 람다 식을 선언할 수 없습니다.
컴파일러에 대한 순환 논리 문제를 만듭니다. `var` 선언은 대입 연산자의 오른쪽에 있는 식의 형식에서 변수의 형식을 확인하도록 컴파일러에 지시합니다. 람다 식에는 컴파일 시간 형식이 없지만 일치하는 모든 대리자 또는 식 형식으로 변환할 수 있습니다. 대리자 또는 식 형식의 변수에 람다 식을 할당하는 경우 람다 식을 시도하고 '담당자' 변수의 시그니처와 일치하는 식 또는 대리자로 변환하도록 컴파일러에 지시하는 것입니다. 컴파일러는 할당의 오른쪽 형식을 할당의 왼쪽 형식과 일치시키려고 해야 합니다. 

할당의 양쪽 모두 대입 연산자의 다른 쪽에 있는 개체를 검사하고 형식이 일치하는지 확인하도록 컴파일러에 지시할 수 없습니다.

C# 언어에서 해당 동작을 지정하는 이유에 대한 세부 정보를 확인하려면 [이 문서](http://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf)(PDF 다운로드)를 참조하세요.




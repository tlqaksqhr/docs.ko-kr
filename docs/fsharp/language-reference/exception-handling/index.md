---
title: "예외 처리(F#)"
description: "예외 처리(F#)"
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ad475c4a-d94e-47d9-b27b-3ff000b65f8e
translationtype: Human Translation
ms.sourcegitcommit: 0a01ec92a90d99fafaacbd3f71f5177e5cf94a68
ms.openlocfilehash: d95aca8c511524f0b9af67b34a5999f885cf3aaf
ms.lasthandoff: 04/05/2017

---

# <a name="exception-handling"></a>예외 처리

이 섹션에서는 F# 언어의 예외 처리 지원에 대해 설명합니다.


## <a name="exception-handling-basics"></a>예외 처리 기본 사항
예외 처리는 .NET Framework의 오류 조건을 처리하는 표준 방법입니다. 따라서 F#을 비롯한 모든 .NET 언어는 이 메커니즘을 지원해야 합니다. *예외*는 오류에 대한 정보를 캡슐화하는 개체입니다. 오류가 발생하면 예외가 발생하고 정상적인 실행이 중지됩니다. 대신, 런타임에서 예외에 대한 적절한 처리기를 검색합니다. 검색은 현재 함수에서 시작하고, 일치하는 처리기를 찾을 때까지 호출자의 계층을 통해 스택을 나아갑니다. 그런 다음 처리기가 실행됩니다.

또한 스택이 해제될 때, 런타임이 `finally` 블록에서 모든 코드를 실행하여 해제 프로세스 중 개체가 올바르게 정리되도록 보장합니다.


## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----|-----------|
|[예외 형식](exception-types.md)|예외 형식을 선언하는 방법에 대해 설명합니다.|
|[예외: `try...with` 식](the-try-with-expression.md)|예외 처리를 지원하는 언어 구문에 대해 설명합니다.|
|[예외: `try...finally` 식](the-try-finally-expression.md)|예외가 throw될 때 스택이 해제되므로 정리 코드를 실행할 수 있는 언어 구문에 대해 설명합니다.|
|[예외: `raise` 함수](the-raise-Function.md)|예외 개체를 throw하는 방법에 대해 설명합니다.|
|[예외: `failwith` 함수](the-failwith-function.md)|일반 F# 예외를 생성하는 방법에 대해 설명합니다.|
|[예외: `invalidArg` 함수](the-invalidArg-function.md)|잘못된 인수 예외를 생성하는 방법에 대해 설명합니다.|

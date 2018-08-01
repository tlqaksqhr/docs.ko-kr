---
title: global 상황별 키워드(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: 79e0184f58ffc6232038abdd3d9f852147d5732c
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404290"
---
# <a name="global-c-reference"></a>global(C# 참조)

`global` 상황별 키워드가 [:: 연산자](../operators/namespace-alias-qualifer.md) 앞에 배치되는 경우, 이 키워드는 전역 네임스페이스를 가리킵니다. 이는 모든 C# 프로그램의 기본 네임스페이스이며 다른 경우에는 명명되지 않습니다. 자세한 내용은 [방법: 전역 네임스페이스 별칭 사용](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)을 참조하세요.

## <a name="example"></a>예

다음 예제에서는 `global` 상황별 키워드를 사용하여 `TestApp` 클래스가 전역 네임스페이스에 정의되도록 지정하는 방법을 보여 줍니다.

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a>참고 항목

[네임스페이스](../../programming-guide/namespaces/index.md)
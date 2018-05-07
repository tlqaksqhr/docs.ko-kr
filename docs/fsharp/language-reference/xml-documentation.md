---
title: XML 문서(F#)
description: '주석에서 문서를 생성 하는 것에 대 한 지원 F #에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 8bdea89ac810851af07d3aedbbb17d5d90a92ff8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xml-documentation"></a>XML 문서

삼중 슬래시 (/ / /)를 통해 문서를 생성할 수 있습니다 코드 주석을 F #에서. XML 주석 코드 파일 (.fs) 또는 (.fsi) 서명 파일의 선언 앞 입력할 수 있습니다.


## <a name="generating-documentation-from-comments"></a>주석에서 문서 생성
F #에서 주석에서 문서를 생성 하는 것에 대 한 지원은 동일 하 게 다른.NET Framework 언어로 합니다. 다른.NET Framework 언어와 마찬가지로 [-doc 컴파일러 옵션](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) Sandcastle 같은 도구를 사용 하 여 설명서로 변환할 수 있는 정보를 포함 하는 XML 파일을 만들 수 있습니다. 일반적으로 다른.NET Framework 언어로 작성 되는 어셈블리와 함께 사용 하기 위해 디자인 된 도구를 사용 하 여 생성 한 문서는 F # 구문의 컴파일된 형태를 기반으로 하는 Api의 보기를 생성 합니다. 도구 구체적으로 F #을 지원 하지 않는 한 이러한 도구에 의해 생성 된 문서에는 F # 보기 API의 일치 하지 않습니다.

XML에서 문서를 생성 하는 방법에 대 한 자세한 내용은 참조 [XML 문서 주석 &#40;C&#35; 프로그래밍 가이드&#41;](https://msdn.microsoft.com/library/b2s063f7)합니다.


## <a name="recommended-tags"></a>권장된 태그
XML 문서 주석 작성 하는 방법은 두 가지가 있습니다. 하나를 작성 하는 방법 설명서는 삼중 슬래시 주석에서 직접 XML 태그를 사용 하지 않고입니다. 이 작업을 수행 하는 경우 전체 주석 텍스트 바로 뒤에 오는 코드 구문에 대 한 요약 설명서로 가져옵니다. 각 구문에 대 한 간단한 요약을 작성 하려는 경우이 메서드를 사용 합니다. 또 다른 방법은 더 구조화 된 문서를 제공 하려면 XML 태그를 사용 하는 것입니다. 두 번째 방법은 사용 하는 방법을 간단히 설명, 추가적인 주의 사항은, 각 매개 변수 및 형식 매개 변수 및, 발생 한 예외에 대 한 설명서 및 반환 값에 대 한 설명을 대 한 별도 참고를 지정할 수 있습니다. 다음 표에서 F # XML 코드 주석에서 인식 되는 XML 태그를 설명 합니다.



|태그 구문|설명|
|----------|-----------|
|**&lt;c&gt;***텍스트***&lt;/c&gt;**|지정 하는 *텍스트* 코드입니다. 이 태그는 문서 생성기에서 사용 중인 코드에 대 한 적합 한 글꼴의 텍스트를 표시 하려면 사용할 수 있습니다.|
|**&lt;요약&gt;***텍스트*** &lt; /요약&gt;**|지정 하는 *텍스트* 프로그램 요소에 대 한 간단한 설명입니다. 설명은 일반적으로 한 두 문장.|
|**&lt;주의&gt;***텍스트*** &lt; /r&gt;**|지정 하는 *텍스트* 프로그램 요소에 대 한 보충 정보를 포함 합니다.|
|**&lt;param 이름 = "***이름***"&gt;***설명***&lt;/param&gt;**|이름 및 함수 또는 메서드 매개 변수에 대 한 설명을 지정합니다.|
|**&lt;typeparam 이름 = "***이름***"&gt;***설명***&lt;/typeparam&gt;**|이름 및 형식 매개 변수에 대 한 설명을 지정합니다.|
|**&lt;반환&gt;***텍스트*** &lt; /r&gt;**|지정 하는 *텍스트* 함수 또는 메서드의 반환 값에 설명 합니다.|
|**&lt;예외 cref = "***형식***"&gt;***설명***&lt;/exception&gt;**|생성 될 수 있는 예외 및 throw 되는 상황의 유형을 지정 합니다.|
|**&lt;e e cref = "***참조***"&gt;***텍스트*** &lt; /참조&gt;**|다른 프로그램 요소에 대 한 인라인 링크를 지정합니다. *참조* XML 문서 파일에 표시 되는 이름입니다. *텍스트* 링크에 나타나는 텍스트입니다.|
|**&lt;seealso cref = "***참조***" /&gt;**|다른 형식에 대 한 설명서를 참고 항목 링크를 지정합니다. *참조* XML 문서 파일에 표시 되는 이름입니다. 설명서 페이지 맨 아래에 일반적으로 표시 되는 링크를 참조 하십시오.|
|**&lt;p a r a&gt;***텍스트***&lt;/para&gt;**|텍스트 단락을 지정합니다. 이 내부 텍스트 구분 하는 데 사용 됩니다는 **주의** 태그입니다.|

## <a name="example"></a>예제

### <a name="description"></a>설명
다음은 서명 파일의 일반적인 XML 문서 주석입니다.


### <a name="code"></a>코드
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]
    
## <a name="example"></a>예제

### <a name="description"></a>설명
다음 예제에서는 XML 태그가 없는 하는 대체 방법을 보여 줍니다. 이 예제에서는 전체 텍스트 주석에서 요약으로 간주 됩니다. 요약 태그를 명시적으로 지정 하지 않으면 해야 하지 지정 합니다 다른 태그와 같은 **param** 또는 **반환** 태그입니다.


### <a name="code"></a>코드
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]
    
## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[컴파일러 옵션](compiler-options.md)

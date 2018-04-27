---
title: -결정적
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 273abf8811f04cd7f58599ce3421ca1f17c740d9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="-deterministic"></a>-결정적

컴파일러가 해당 바이트에 대 한 출력은 동일한 입력에 대해 컴파일 간에 동일 어셈블리를 생성 해야 합니다. 

## <a name="syntax"></a>구문

```
-deterministic
```

## <a name="remarks"></a>설명

기본적으로 컴파일러는 타임 스탬프와 난수에서 생성 되는 GUID를 추가 하므로 지정 된 입력 집합에서 컴파일러 출력은 고유 합니다. 사용 하면는 `-deterministic` 를 생성 하는 옵션을 *결정적 어셈블리*, 동일 하 게 유지 입력으로 해당 이진 콘텐츠는 컴파일 간에 동일 하나.

컴파일러는 결정성 목적으로 다음 사항을 고려합니다.

- 명령줄 매개 변수 시퀀스입니다.
- 컴파일러의.rsp 응답 파일의 내용입니다.
- 을 사용 하는 컴파일러의 정확한 버전 및 참조 되는 어셈블리입니다.
- 현재 디렉터리 경로입니다.
- 모든 파일의 이진 내용을 명시적으로 전달 컴파일러에 직접 또는 간접적으로 포함 하 여: 
    - 소스 파일
    - 참조 된 어셈블리
    - 참조 된 모듈
    - 자료
    - 강력한 이름 키 파일
    - @ 응답 파일
    - 분석기
    - 규칙 집합
    - 분석기에서 사용할 수 있는 추가 파일
- (메시지가 생성 되는 진단 및 예외 언어)에 대 한 현재 culture입니다.
- 기본 인코딩은 (또는 현재 코드 페이지) 인코딩을 지정 하지 않은 경우.
- 존재 여부, 존재 하지 않는 및 컴파일러의 검색 경로에 있는 파일의 내용 (예를 들어에 지정 된 `/lib` 또는 `/recurse`).
- 컴파일러 실행 되는 CLR 플랫폼입니다.
- 값 `%LIBPATH%`, 분석기 종속성 로드에 영향을 줄 수입니다.

공개적으로 사용할 수 있는 원본을 때 결정적 컴파일은 출처를 신뢰할 수 있는 이진 컴파일 되었는지 여부를 설정 하는 데 사용할 수 있습니다. 이진 파일에 대 한 변경에 의존 하는 빌드 단계를 실행 해야 하는지 여부를 확인 하기 위한 연속 빌드 시스템에도 유용할 수 있습니다. 

## <a name="see-also"></a>참고 항목
[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
[샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

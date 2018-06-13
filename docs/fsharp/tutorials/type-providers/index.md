---
title: 형식 공급자
description: 'F # 형식 공급자 형식, 속성 및 메서드를 프로그램에서 사용 하기 위해 제공 하는 구성 요소를가 하는 방법에 대해 알아봅니다.'
ms.date: 04/02/2018
ms.openlocfilehash: 82d9afed7d77eae5f8b96854d40e96a32c4fae9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562269"
---
# <a name="type-providers"></a>형식 공급자

F# 형식 공급자는 사용자 프로그램에서 사용할 형식, 속성 및 메서드를 제공하는 구성 요소입니다. 형식 공급자 라는 항목을 생성 **제공 된 형식**, F # 컴파일러에서 생성 하 고 외부 데이터 원본을 기반으로 합니다.

예를 들어, SQL 용 F # 형식 공급자는 관계형 데이터베이스의 테이블 및 열을 나타내는 형식을 생성할 수 있습니다. 실제로 [SQLProvider](https://fsprojects.github.io/SQLProvider/) 형식 공급자가 있습니다.

제공 유형은 입력된 매개 변수를 형식 공급자에 따라 다릅니다. 이러한 입력 (예: JSON 스키마 파일), 샘플 데이터 소스 수 직접 외부 서비스 또는 데이터 원본에 연결 문자열을 가리키는 URL입니다. 형식 공급자는 형식의 그룹이 필요할 때;만 확장 되도록 할 수도 있습니다. 즉, 형식을 프로그램에서 참조 하는 실제로 경우 확장 됩니다. 따라서 강력한 형식으로 온라인 데이터 시장과 같은 대규모 정보 공간의 직접적인 주문형 통합을 허용합니다.

## <a name="generative-and-erased-type-providers"></a>생성 및 지워진 형식 공급자

형식 공급자는 두 가지 형태로 제공: 생성 및 삭제 합니다.

생성 형식 공급자는.NET 형식으로 생성 된 어셈블리에 쓸 수 있는 형식을 생성 합니다. 이렇게 하면 다른 어셈블리의 코드에서 사용할 수 있습니다. 즉, 데이터 원본의 입력 된 표현을 나타내는.NET 형식에 하나 이어야 일반적으로 합니다.

지우기 형식 공급자는 어셈블리 또는 프로젝트에서 생성 된만 사용할 수 있는 형식을 생성 합니다. 유형은 임시입니다. 즉, 어셈블리에 기록 되지 않고 하며 다른 어셈블리의 코드에서 사용 될 수 없습니다. 포함 될 수 있습니다 *지연* 멤버, 잠재적으로 무한 정보 공간에서 제공 하는 사용 유형을 수 있게 해줍니다. 광범위 하 고 상호 연결 된 데이터 원본의 작은 하위 집합을 사용 하는 데 유용 합니다.

## <a name="commonly-used-type-providers"></a>일반적으로 사용 되는 형식 공급자

서로 다른 사용에 대 한 형식 공급자를 포함 하는 다음 널리 사용 되는 라이브러리:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) JSON, XML, CSV, 및 HTML 문서 형식 및 리소스에 대 한 형식 공급자가 포함 됩니다.
- [SQLProvider](https://fsprojects.github.io/SQLProvider/) 이러한 데이터 원본에 대 한 쿼리 개체의 매핑 및 F # LINQ를 통해 관계 데이터베이스에 대 한 강력한 형식의 액세스를 제공 합니다.
- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) 컴파일 시간에 대 한 형식 공급자 집합을 체크 F #에서 T-SQL의 포함 합니다.
- [Azure 저장소 형식 공급자](https://fsprojects.github.io/AzureStorageTypeProvider/) Azure Blob, 테이블 및 큐, 프로그램 전체에서 문자열로 리소스 이름을 지정할 필요 없이 이러한 리소스에 액세스할 수 있도록 하기 위한 형식을 제공 합니다.
- [FSharp.Data.GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) 포함는 **GraphQLProvider**, URL에서 지정한 GraphQL 서버 기반 형식을 제공 합니다.

필요한 경우 다음을 수행할 수 있습니다 [사용자 고유의 사용자 지정 형식 공급자를 만들](creating-a-type-provider.md), 또는 다른 사용자가 만든 형식 공급자를 참조 합니다. 예를 들어 조직에 규모가 크고 점점 더 수가 증가하는 명명된 데이터 집합(각각 자체적으로 안정적인 데이터 스키마 포함)을 제공하는 데이터 서비스가 있다고 가정합니다. 강력한 방식으로 스키마를 읽고 프로그래머에 설정된 사용할 수 있는 최신 데이터 집합을 제공하는 형식 공급자를 만들도록 선택할 수 있습니다.

## <a name="see-also"></a>참고 항목
[자습서: 형식 공급자 만들기](creating-a-type-provider.md)

[F# 언어 참조](../../language-reference/index.md)

[Visual F#](../../index.md)

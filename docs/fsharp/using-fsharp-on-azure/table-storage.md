---
title: "F #을 사용 하 여 Azure 테이블 저장소 시작"
description: "Azure 테이블 저장소에는 NoSQL 데이터 저장소를 사용 하 여 클라우드에서 구조화 된 데이터를 저장 합니다."
keywords: "visual f #, f #, 기능 프로그래밍,.NET,.NET Core를 Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9e5d6cea-a98c-461e-a5cc-75f1d154eafd
ms.openlocfilehash: bf833a96809768011f26df35332ab2372ced2aaf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-table-storage-using-f"></a>F #을 사용 하 여 Azure 테이블 저장소 시작 #

Azure 테이블 저장소는 클라우드에서 구조화 된 NoSQL 데이터를 저장 하는 서비스입니다. 테이블 저장소는 schemaless 디자인에 키/특성 저장소입니다. 테이블 저장소 schemaless 이기 때문에 응용 프로그램 evolve 필요에 따라 데이터에 맞게 쉽습니다. 데이터에 대 한 액세스가 신속 하 고 모든 종류의 응용 프로그램에 대 한 비용 효율적인 합니다. 테이블 저장소 일반적으로 보다 훨씬 낮습니다 비용에 유사한 데이터 볼륨에 대 한 기존의 SQL 합니다.

웹 응용 프로그램, 주소록, 장치 정보 및 다른 유형의 서비스에 필요한 메타 데이터에 대 한 사용자 데이터와 같이 유연한 데이터 집합을 저장할 테이블 저장소를 사용할 수 있습니다. 테이블의 모든 엔터티 수를 저장할 수 있습니다 및 저장소 계정에는 임의 개수의 테이블 저장소 계정의 용량 제한까지 포함 될 수 있습니다.

### <a name="about-this-tutorial"></a>이 자습서 정보

이 자습서에서는 만들기 및 테이블을 삭제 및 삽입, 업데이트, 삭제 및 테이블 데이터를 쿼리를 포함 하 여 Azure 테이블 저장소를 사용 하 여 몇 가지 일반적인 작업을 수행 하는 F # 코드를 작성 하는 방법을 보여 줍니다.

테이블 저장소의 개념적인 개요를 참조 하십시오 [테이블 저장소에 대 한.NET 가이드](/azure/storage/storage-dotnet-how-to-use-tables)

## <a name="prerequisites"></a>필수 구성 요소

이 가이드를 사용 하려면 먼저 [Azure 저장소 계정 만들기](/azure/storage/storage-create-storage-account)합니다.
또한이 계정에 대 한 저장소 액세스 키를 해야 합니다.

## <a name="create-an-f-script-and-start-f-interactive"></a>만들기는 F # 스크립트와 시작 F # 대화형

이 문서에 있는 예제에서 F # 응용 프로그램 또는 F # 스크립트에서 사용할 수 있습니다. F # 스크립트를 만들려면으로 파일 만들기는 `.fsx` 예를 들어 확장 `tables.fsx`, F # 개발 환경에서 합니다.

를 사용 하 여 한 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 를 설치 하는 `WindowsAzure.Storage` 패키지와 참조 `WindowsAzure.Storage.dll` 는 를사용하여스크립트에서`#r`지시문입니다. Microsoft.Azure 네임 스페이스를 가져오기 위해 'Microsoft.WindowsAzure.ConfigurationManager'에 대해 다시를 수행 합니다.

### <a name="add-namespace-declarations"></a>네임 스페이스 선언을 추가합니다

다음 추가 `open` 문을의 맨 위에 `tables.fsx` 파일:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>연결 문자열 가져오기

이 자습서에 대 한 Azure 저장소 연결 문자열이 필요 합니다. 연결 문자열에 대 한 자세한 내용은 참조 [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.

자습서에서는 다음과 같이 스크립트에 연결 문자열을 입력 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

그러나이 방법은 **좋지** 를 실제 프로젝트. 저장소 계정 키 저장소 계정에 대 한 루트 암호와 비슷합니다. 항상 저장소 계정 키를 보호 해야 합니다. 하드 코딩을 다른 사용자에 게 액세스가 허용 되는 일반 텍스트 파일에 저장 하거나 다른 사용자에 게 배포 하지 마십시오. 노출 되었다고 판단 되 면 Azure 포털을 사용 하 여 키를 다시 생성할 수 있습니다.

실제 응용 프로그램 저장소 연결 문자열을 유지 관리 하는 가장 좋은 방법은 구성 파일에는 합니다. 구성 파일에서 연결 문자열을 페치 하려면이 수행할 수 있습니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

Azure 구성 관리자를 사용 하는 것은 선택 사항입니다. .NET Framework 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 유형입니다.

### <a name="parse-the-connection-string"></a>연결 문자열을 구문 분석

연결 문자열을 구문 분석 하려면 다음을 사용 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

이 반환 됩니다는 `CloudStorageAccount`합니다.

### <a name="create-the-table-service-client"></a>테이블 서비스 클라이언트 만들기

`CloudTableClient` 클래스를 사용 하면 테이블 및 테이블 저장소에 저장 된 엔터티를 검색할 수 있습니다. 서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

이제 데이터를 읽고 데이터를 테이블 저장소에 기록 하는 코드를 작성할 준비가 되었습니다.

## <a name="create-a-table"></a>테이블 만들기

이 예제에는 아직 없는 경우 테이블을 만드는 방법을 보여 줍니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

## <a name="add-an-entity-to-a-table"></a>테이블에 엔터티 추가

상속 되는 형식에 엔터티 `TableEntity`합니다. 확장할 수 있습니다 `TableEntity` , 원하는 어떤 방법으로든 있지만 형식이 *해야* 매개 변수 없는 생성자가 있습니다. 둘 다 있는 속성만 `get` 및 `set` Azure 테이블에 저장 됩니다.

엔터티의 파티션과 행 키는 테이블의 엔터티를 고유 하 게 식별 합니다. 동일한 파티션 키를 가진 엔터티가 다른 파티션 키를 사용 하는 것 보다 더 빠르게 쿼리할 수 있지만 다양 한 파티션 키를 사용 하 여 병렬 작업의 확장성을 높일 수 있습니다.

예로 `Customer` 를 사용 하 여 `lastName` 파티션 키로 및 `firstName` 행 키로 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

이제 추가 우리의 `Customer` 테이블에 있습니다. 이렇게 하려면 만듭니다는 `TableOperation` 하는 테이블에서 실행 됩니다. 이 경우에 만듭니다는 `Insert` 작업 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

## <a name="insert-a-batch-of-entities"></a>엔터티 일괄 처리를 삽입 합니다.

엔터티 일괄 처리를 단일 쓰기 작업을 사용 하 여 테이블에 삽입할 수 있습니다. 일괄 처리 작업을 사용 하면 단일 실행으로 작업을 결합할 수 있도록 하지만 몇 가지 제한 사항이 있습니다.

- 업데이트를 수행할 수 있습니다, 삭제 하 고 동일한 일괄 처리 작업에서 삽입 합니다.
- 일괄 처리 작업을 100 개까지 엔터티를 포함할 수 있습니다.
- 일괄 처리 작업의 모든 엔터티가 동일한 파티션 키에 있어야 합니다.
- 일괄 작업에서 쿼리를 수행 하는 가능 하지만 일괄 처리에서 유일한 작업 이어야 합니다.

두 삽입 일괄 처리 작업으로 결합 하는 일부 코드는 다음과 같습니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

## <a name="retrieve-all-entities-in-a-partition"></a>파티션의 모든 엔터티 검색

파티션에서 모든 엔터티의 테이블을 쿼리를 사용 하 여 한 `TableQuery` 개체입니다. 여기에서 필터링 할 엔터티에 대 한 "버스터"은 파티션 키입니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L80)]

이제 결과 인쇄 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


## <a name="retrieve-a-range-of-entities-in-a-partition"></a>다양 한 파티션에 엔터티를 검색 합니다.

파티션의 모든 엔터티를 쿼리 하려는 하지 않는 경우에 행 키 필터와 파티션 키 필터를 결합 하 여 범위를 지정할 수 있습니다. 여기에서는 두 개의 필터를 사용 하면 "버스터" 파티션에 있는 모든 엔터티를 가져올 위치 행 키 (이름) 문자로 시작 알파벳의 "M" 보다 이전입니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

이제 결과 인쇄 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

## <a name="retrieve-a-single-entity"></a>단일 엔터티를 검색 합니다.

단일, 특정 엔터티를 검색 하는 쿼리를 작성할 수 있습니다. 사용 하는 여기에서 `TableOperation` "Larry 버스터" 고객을 지정할 수 있습니다. 컬렉션을 대신 얻게는 `Customer`합니다. 쿼리에서 파티션 키와 행 키를 지정 하는 테이블 서비스에서 단일 엔터티를 검색 하는 가장 빠른 방법은.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

이제 결과 인쇄 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


## <a name="replace-an-entity"></a>엔터티를 대체 합니다.

엔터티를 업데이트 하려면 테이블 서비스에서 검색, 엔터티 개체를 수정 하 고 다음 변경 내용을 사용 하 여 테이블 서비스에 다시 저장 된 `Replace` 작업 합니다. 이렇게 하면 서버에서 엔터티는 작업은 실패 하는 경우, 검색 된 이후 변경 되지 않은 엔터티는 서버에서 완전히 대체 됩니다. 이 오류는 응용 프로그램에서 다른 소스 로부터 변경 내용을 실수로 덮어쓰지 않도록 되려고 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

## <a name="insert-or-replace-an-entity"></a>삽입 또는 바꾸기 기능 엔터티

경우에 따라 엔터티 테이블에 있는 경우에 대해 모릅니다. 그렇지 않으면에 저장 된 현재 값은 더 이상 필요 하지 않으며 사용할 수 있습니다 `InsertOrReplace` 엔터티를 만들거나 해당 상태에 관계 없이, 있는 경우 대체 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L140)]

## <a name="query-a-subset-of-entity-properties"></a>엔터티 속성의 하위 집합을 쿼리

테이블 쿼리 전체가 아닌 엔터티에서 몇 개의 속성을 검색할 수 있습니다. 투영 이라는이 방법을 큰 엔터티를 위해 특별히 쿼리 성능을 향상 시킬 수 있습니다. 만 전자 메일 주소를 사용 하 여 반환 여기서 `DynamicTableEntity` 및 `EntityResolver`합니다. 참고가이 코드는 테이블 서비스 계정을 사용 하는 경우에 실행 되므로 프로젝션 로컬 저장소 에뮬레이터에서 지원 되지 않습니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L146-L157)]

## <a name="retrieve-entities-in-pages-asynchronously"></a>페이지에서 엔터티를 비동기적으로 검색

많은 엔터티를 읽고 있는 모두 반환을 기다리지 않고 검색 된 때 처리 하려는 경우에 조각화 된 쿼리를 사용할 수 있습니다. 여기에서 있습니다 결과 페이지에서 사용 하 여 반환 비동기 워크플로 반환할 결과의 큰 집합에 대 한 대기 하는 동안 실행이 차단 되지 않도록 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L177)]

하면 이제이 계산이 동기적으로 실행 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L179-L179)]

## <a name="delete-an-entity"></a>엔터티 삭제

검색 한 후 엔터티를 삭제할 수 있습니다. 엔터티를 업데이트할와 마찬가지로 엔터티 것으로 검색 한 이후 변경 된 경우 실패 합니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L185-L186)]

## <a name="delete-a-table"></a>테이블 삭제

저장소 계정에서 테이블을 삭제할 수 있습니다. 삭제 된 테이블 삭제 후 일정 기간에 대 한 다시 만들어야 사용할 수 없습니다.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L192-L192)]

## <a name="next-steps"></a>다음 단계

테이블 저장소의 기본 사항 학습 한, 했으므로 더 복잡 한 저장소 작업에 대 한 자세한 내용은 다음이 링크를 수행:

- [.NET 참조 용 저장소 클라이언트 라이브러리](http://go.microsoft.com/fwlink/?LinkID=390731&clcid=0x409)
- [Azure 저장소 형식 공급자](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [Azure 저장소 팀 블로그](http://blogs.msdn.com/b/windowsazurestorage/)
- [연결 문자열 구성](http://msdn.microsoft.com/library/azure/ee758697.aspx)
- [.NET에서 Azure 테이블 저장소 시작](https://azure.microsoft.com/documentation/samples/storage-table-dotnet-getting-started/)

---
title: "F #을 사용 하 여 Azure 큐 저장소 시작"
description: "Azure 큐는 안정적이 고 비동기 응용 프로그램 구성 요소 간의 메시징을 제공 합니다. 메시징 사용 독립적으로 확장할 응용 프로그램 구성 요소를 클라우드입니다."
keywords: "visual f #, f #, 기능 프로그래밍,.NET,.NET Core를 Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 70dc554c-8f4d-42a7-8e2a-6438657d012a
ms.openlocfilehash: 8ec4652bab591dedc687d22c617b9466bc351f10
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/13/2018
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>F #을 사용 하 여 Azure 큐 저장소 시작 #

Azure 큐 저장소는 클라우드 응용 프로그램 구성 요소 간에 메시징을 제공 합니다. 눈금에 대 한 응용 프로그램을 디자인, 응용 프로그램 구성 요소는 종종 분리, 있습니다 수를 독립적으로 확장할 수 있도록. 큐 저장소 바탕 화면, 온-프레미스 서버 또는 모바일 장치는 클라우드에서 실행 중인 여부 비동기 메시징 응용 프로그램 구성 요소 간의 통신을 제공 합니다. 큐 저장소는 비동기 작업을 관리 하 고 프로세스 작업 흐름을 작성도 지원 합니다.

### <a name="about-this-tutorial"></a>이 자습서 정보

이 자습서에서는 Azure 큐 저장소를 사용 하 여 몇 가지 일반적인 작업에 대 한 F # 코드를 작성 하는 방법을 보여 줍니다. 다루는 작업 만들기 및 큐를 삭제 하 고 추가, 읽기 및 큐 메시지 삭제를 포함 합니다.

큐 저장소의 개념적인 개요를 참조 하십시오 [큐 저장소에 대 한.NET 가이드](/azure/storage/storage-dotnet-how-to-use-queues)합니다.

## <a name="prerequisites"></a>필수 구성 요소

이 가이드를 사용 하려면 먼저 [Azure 저장소 계정 만들기](/azure/storage/storage-create-storage-account)합니다.
또한이 계정에 대 한 저장소 액세스 키를 해야 합니다.

## <a name="create-an-f-script-and-start-f-interactive"></a>만들기는 F # 스크립트와 시작 F # 대화형

이 문서에 있는 예제에서 F # 응용 프로그램 또는 F # 스크립트에서 사용할 수 있습니다. F # 스크립트를 만들려면으로 파일 만들기는 `.fsx` 예를 들어 확장 `queues.fsx`, F # 개발 환경에서 합니다.

를 사용 하 여 한 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 를 설치 하는 `WindowsAzure.Storage` 패키지와 참조 `WindowsAzure.Storage.dll` 는 를사용하여스크립트에서`#r`지시문입니다.

### <a name="add-namespace-declarations"></a>네임 스페이스 선언을 추가합니다

다음 추가 `open` 문을의 맨 위에 `queues.fsx` 파일:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>연결 문자열 가져오기

이 자습서에 대 한 Azure 저장소 연결 문자열이 필요 합니다. 연결 문자열에 대 한 자세한 내용은 참조 [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.

자습서에서는 다음과 같이 스크립트에 연결 문자열을 입력 합니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

그러나이 방법은 **좋지** 를 실제 프로젝트. 저장소 계정 키 저장소 계정에 대 한 루트 암호와 비슷합니다. 항상 저장소 계정 키를 보호 해야 합니다. 하드 코딩을 다른 사용자에 게 액세스가 허용 되는 일반 텍스트 파일에 저장 하거나 다른 사용자에 게 배포 하지 마십시오. 노출 되었다고 판단 되 면 Azure 포털을 사용 하 여 키를 다시 생성할 수 있습니다.

실제 응용 프로그램 저장소 연결 문자열을 유지 관리 하는 가장 좋은 방법은 구성 파일에는 합니다. 구성 파일에서 연결 문자열을 페치 하려면이 수행할 수 있습니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

Azure 구성 관리자를 사용 하는 것은 선택 사항입니다. .NET Framework 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 유형입니다.

### <a name="parse-the-connection-string"></a>연결 문자열을 구문 분석

연결 문자열을 구문 분석 하려면 다음을 사용 합니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

이 반환 됩니다는 `CloudStorageAccount`합니다.

### <a name="create-the-queue-service-client"></a>큐 서비스 클라이언트 만들기

`CloudQueueClient` 클래스를 사용 하면 큐 저장소에 저장 된 큐를 검색할 수 있습니다. 서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

이제 데이터를 읽고 큐 저장소에 데이터를 기록 하는 코드를 작성할 준비가 되었습니다.

## <a name="create-a-queue"></a>큐 만들기

이 예제에는 존재 하지 않는 경우 큐를 만드는 방법을 보여 줍니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>큐에 메시지를 삽입 합니다.

기존 큐에 메시지를 삽입 하려면 먼저 새 만들려면 `CloudQueueMessage`합니다. 그런 다음 호출 하 여 `AddMessage` 메서드. A `CloudQueueMessage` 를 u t F-8 형식 문자열 중 하나에서 생성 또는 `byte` 배열은 다음과 같이 합니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>다음 메시지 엿보기

호출 하 여 큐에서 제거 하지 않고 큐 앞의 메시지를 피킹할 수 있습니다는 `PeekMessage` 메서드.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>다음 메시지 처리에 대 한 가져오기

호출 하 여 처리를 위해 큐의 앞에 메시지를 검색할 수 있습니다는 `GetMessage` 메서드.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

나중에 사용 하 여 메시지를 성공적으로 처리를 나타낼 `DeleteMessage`합니다.

## <a name="change-the-contents-of-a-queued-message"></a>대기 중인된 메시지의 내용을 변경합니다

검색된 메시지 내부에서 큐의 내용을 변경할 수 있습니다. 메시지 작업 작업을 나타내는 경우에 작업 작업의 상태를 업데이트 하려면이 기능을 사용할 수 있습니다. 다음 코드는 새 내용으로 큐 메시지를 업데이트 하 고 다른 60 초를 확장 하 여 표시 제한 시간을 설정 합니다. 이 메시지와 관련 된 작업의 상태를 저장 하 고 클라이언트 메시지에 대해 작업을 계속 하려면 다른 분을 제공 합니다. 큐 메시지의 처리 단계 하드웨어 또는 소프트웨어 오류로 인해 실패 한 경우 처음부터 다시 시작 하지 않고도 여러 단계의 워크플로 추적 하기 위해이 방법을 사용할 수 있습니다. 일반적으로는 다시 시도 횟수를 보관할 때 하 고 메시지를 몇 번 이상 다시 시도 하는 경우 파일을 삭제 합니다. 이 처리 될 때마다 응용 프로그램 오류를 트리거하는 메시지 로부터 보호 됩니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>다음 메시지 큐에서 제거

코드에는 두 단계로 큐에서 메시지를 큐 제거 합니다. 호출 하는 경우 `GetMessage`를 큐에 있는 다음 메시지로 이동 합니다. 반환 된 메시지 `GetMessage` 이 큐에서 메시지를 읽을 다른 모든 코드 보이지 않게 합니다. 이 메시지 기본적으로 30 초 동안 보이지 않는 유지 됩니다. 메시지 큐에서 제거를 마치려면 호출 또한 해야 `DeleteMessage`합니다. 메시지를 제거 하는이 두 단계 과정 통해 있는 코드에 하드웨어 또는 소프트웨어 오류로 인해 메시지를 처리 하지 못하는 경우 코드의 다른 인스턴스 수 동일한 메시지가 다시 시도 하십시오 있습니다. 코드 호출 `DeleteMessage` 메시지 처리 된 후 마우스 오른쪽 단추로 합니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>비동기 워크플로 사용 하 여 일반적인 큐 저장소 Api

이 예제에서는 일반적인 큐 저장소 Api는 비동기 워크플로 사용 하는 방법을 보여 줍니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>메시지를 역직렬화 큐에 대 한 추가 옵션

두 가지 방법으로 큐에서 메시지 검색을 사용자 지정할 수 있습니다.
첫째, 32) (최대 메시지 일괄 처리를 가져올 수 있습니다. 둘째, 많거나 완벽 하 게 각 메시지를 처리 하는 시간이 적은 코드를 허용 더 길거나 더 짧은 표시 안 함 시간 초과 설정할 수 있습니다. 다음 코드 예제에서는 `GetMessages` 보려면 20 하나로 메시지를 호출 하 고 다음 각 메시지를 처리 합니다. 또한 각 메시지에 대해 5 분에 표시 안 함 시간 제한을 설정합니다. 이와 동시에 모든 메시지에 대해 5 분을 시작 하는 참고 후 일 분에 대 한 호출 이후 경과한 `GetMessages`, 모든 메시지는 삭제 되지 않았으므로 다시 표시 됩니다.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>큐 길이 가져오기

큐에 있는 메시지 수의 예측을 얻을 수 있습니다. `FetchAttributes` 메서드 요청 큐 서비스의 메시지 수를 포함 하 여 큐 특성을 검색할 수 있습니다. `ApproximateMessageCount` 하 여 검색할 마지막 값을 반환 하는 속성은 `FetchAttributes` 큐 서비스를 호출 하지 않고 메서드.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>큐 삭제

호출 하는 큐와 그 안에 포함 된 모든 메시지를 삭제 하려면는 `Delete` 큐 개체에서 메서드.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>다음 단계

큐 저장소의 기본 사항 학습 한, 했으므로 더 복잡 한 저장소 작업에 대 한 자세한 내용은 다음이 링크를 따릅니다.

- [.NET 용 azure 저장소 Api](/dotnet/api/overview/azure/storage)
- [Azure 저장소 형식 공급자](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Azure 저장소 팀 블로그](http://blogs.msdn.com/b/windowsazurestorage/)
- [Azure 저장소 연결 문자열 구성](/azure/storage/common/storage-configure-connection-string)
- [Azure 저장소 서비스 REST API 참조](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

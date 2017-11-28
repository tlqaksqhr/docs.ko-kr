---
title: "F #을 사용 하 여 Azure 파일 저장소 시작"
description: "클라우드 Azure 파일 저장소에 파일 데이터를 저장 및 Azure 가상 컴퓨터 (VM)에서 클라우드 파일 공유를 탑재 또는 온-프레미스 응용 프로그램에서 Windows를 실행 합니다."
keywords: "visual f #, f #, 기능 프로그래밍,.NET,.NET Core를 Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5c26a0aa-186e-476c-9f87-e0191754579e
ms.openlocfilehash: 66b2503744e9024deac3d6dabea57da4fd393bd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-file-storage-using-f"></a>F #을 사용 하 여 Azure 파일 저장소 시작 #

Azure 파일 저장소 파일 공유는 표준을 사용 하 여 클라우드를 제공 하는 서비스는 [서버 메시지 블록 (SMB) 프로토콜](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)합니다. SMB 2.1과 SMB 3.0을 둘 다 지원 됩니다. Azure 파일 저장소를 신속 하 고 비용이 많이 드는 다시 작성 하지 않고 Azure에 파일 공유를 사용 하는 레거시 응용 프로그램을 마이그레이션할 수 있습니다. Azure 가상 컴퓨터 또는 클라우드 서비스 또는 온-프레미스 클라이언트에서 실행 중인 응용 프로그램 일반적인 SMB 공유를 탑재 하는 데스크톱 응용 프로그램 처럼 클라우드에서 파일 공유를 탑재할 수 있습니다. 응용 프로그램 구성 요소를 개수에 관계 없이 다음 탑재 하 고 수 파일 저장소 공유에 동시에 액세스 합니다.

파일 저장소의 개념적인 개요를 참조 하십시오 [파일 저장소에 대 한.NET 가이드](/azure/storage/storage-dotnet-how-to-use-files)합니다.

## <a name="prerequisites"></a>필수 구성 요소

이 가이드를 사용 하려면 먼저 [Azure 저장소 계정 만들기](/azure/storage/storage-create-storage-account)합니다.
또한이 계정에 대 한 저장소 액세스 키를 해야 합니다.

## <a name="create-an-f-script-and-start-f-interactive"></a>만들기는 F # 스크립트와 시작 F # 대화형

이 문서에 있는 예제에서 F # 응용 프로그램 또는 F # 스크립트에서 사용할 수 있습니다. F # 스크립트를 만들려면으로 파일 만들기는 `.fsx` 예를 들어 확장 `files.fsx`, F # 개발 환경에서 합니다.

를 사용 하 여 한 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 를 설치 하는 `WindowsAzure.Storage` 패키지와 참조 `WindowsAzure.Storage.dll` 는 를사용하여스크립트에서`#r`지시문입니다.

### <a name="add-namespace-declarations"></a>네임 스페이스 선언을 추가합니다

다음 추가 `open` 문을의 맨 위에 `files.fsx` 파일:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>연결 문자열 가져오기

이 자습서에 대 한 Azure 저장소 연결 문자열이 필요 합니다. 연결 문자열에 대 한 자세한 내용은 참조 [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.

자습서에서는 다음과 같이 스크립트에 연결 문자열을 입력 합니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

그러나이 방법은 **좋지** 를 실제 프로젝트. 저장소 계정 키 저장소 계정에 대 한 루트 암호와 비슷합니다. 항상 저장소 계정 키를 보호 해야 합니다. 하드 코딩을 다른 사용자에 게 액세스가 허용 되는 일반 텍스트 파일에 저장 하거나 다른 사용자에 게 배포 하지 마십시오. 노출 되었다고 판단 되 면 Azure 포털을 사용 하 여 키를 다시 생성할 수 있습니다.

실제 응용 프로그램 저장소 연결 문자열을 유지 관리 하는 가장 좋은 방법은 구성 파일에는 합니다. 구성 파일에서 연결 문자열을 페치 하려면이 수행할 수 있습니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Azure 구성 관리자를 사용 하는 것은 선택 사항입니다. .NET Framework 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 유형입니다.

### <a name="parse-the-connection-string"></a>연결 문자열을 구문 분석

연결 문자열을 구문 분석 하려면 다음을 사용 합니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

이 반환 됩니다는 `CloudStorageAccount`합니다.

### <a name="create-the-file-service-client"></a>파일 서비스 클라이언트 만들기

`CloudFileClient` 유형을 프로그래밍 방식으로 파일 저장소에 저장 된 파일을 사용할 수 있습니다. 서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

이제 데이터를 읽고 데이터 파일 저장소를 기록 하는 코드를 작성할 준비가 되었습니다.

## <a name="create-a-file-share"></a>파일 공유 만들기

이 예제에는 아직 없는 경우 파일 공유를 만드는 방법을 보여 줍니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>루트 디렉터리 및 하위 디렉터리 만들기

루트 디렉터리를 가져올 여기에서 가져오고, 루트의 하위 디렉터리입니다. 아직 없는 경우 모두 만듭니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>텍스트 파일로 업로드

이 예제에서는 텍스트 파일을 업로드 하는 방법을 보여 줍니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>파일 파일의 로컬 복사본을 다운로드

여기 파일을 다운로드 하 여 방금 만든 로컬 파일에 내용을 추가 합니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>파일 공유에 대 한 최대 크기 설정

아래 예제에는 공유에 대 한 현재 사용량을 확인 하는 방법과 공유에 대 한 할당량을 설정 하는 방법을 보여 줍니다. `FetchAttributes`호출 하는 공유의 채우기 `Properties`, 및 `SetProperties` Azure 파일 저장소에 로컬 변경 내용을 전파 하 합니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>파일 또는 파일 공유에 대 한 공유 액세스 서명 생성

파일 공유 또는 개별 파일에 대 한 공유 액세스 서명 (SAS)를 생성할 수 있습니다. 또한 공유 액세스 서명을 관리 파일 공유에는 공유 액세스 정책을 만들 수 있습니다. 공유 액세스 정책 만들기 좋습니다 해야 손상 되 면 SAS를 해지 하는 수단을 제공 합니다.

공유를 만들면 여기에서 정책을 공유에 액세스 하 고 다음 해당 정책을 사용 하 여 파일 공유에 대 한 SAS에 대 한 제약 조건을 제공 합니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

만들기 및 공유 액세스 서명을 사용 하는 방법에 대 한 자세한 내용은 참조 [를 사용 하 여 공유 액세스 서명 (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) 및 [만들고 사용 하 여 Blob 저장소 SAS](/azure/storage/storage-dotnet-shared-access-signature-part-2)합니다.

### <a name="copy-files"></a>파일 복사

파일에 파일을 다른 파일이 나 blob 또는 blob에 복사할 수 있습니다. 파일 또는 blob에 파일을 blob를 복사 하는 경우 있습니다 *해야* 동일한 저장소 계정 내에서 복사 하는 경우에 원본 개체를 인증 하는 공유 액세스 서명 (SAS)를 사용 합니다.

### <a name="copy-a-file-to-another-file"></a>다른 파일에 파일을 복사 합니다.

여기에서 다른 파일 공유와 같은 공유에 파일을 복사합니다. 이 복사 작업은 동일한 저장소 계정에서 파일 간 복사를 하기 때문에 복사 하려면 공유 키 인증을 사용할 수 있습니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Blob에 파일을 복사 합니다.

파일을 만들면 여기서 동일한 저장소 계정 내에서 blob에 복사 합니다. 복사 작업 중 소스 파일에 대 한 액세스를 인증 하는 서비스를 사용 하 여 소스 파일에 대 한 SAS를 만들어야 합니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

파일에 동일한 방법으로 blob을 복사할 수 있습니다. 소스 개체가 blob 인 경우에 복사 작업 중 해당 blob에 대 한 액세스를 인증 하는 SAS를 생성 하십시오.

## <a name="troubleshooting-file-storage-using-metrics"></a>파일 저장소 메트릭을 사용 하 여 문제 해결

Azure 저장소 분석 파일 저장소에 대 한 메트릭을 지원합니다. 메트릭 데이터를 요청을 추적 하 고 문제를 진단 사용할 수 있습니다.

파일 저장소에 대 한 메트릭을 사용 하도록 설정할 수는 [Azure 포털](https://portal.azure.com), 다음과 같이 F #에서 수행할 수 있습니다.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>다음 단계

Azure 파일 저장소에 대 한 자세한 내용은 다음이 링크를 참조 합니다.

### <a name="conceptual-articles-and-videos"></a>개념 문서 및 비디오

- [Azure 파일 저장소: 개설 클라우드 Windows 및 Linux 용 SMB 파일 시스템](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Linux에서 Azure 파일 저장소를 사용 하는 방법](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>도구 파일 저장소에 대 한 지원

- [Azure 저장소에서 Azure PowerShell을 사용 하 여](/azure/storage/storage-powershell-guide-full)
- [Microsoft Azure 저장소와 AzCopy를 사용 하는 방법](/azure/storage/storage-use-azcopy)
- [Azure 저장소와 Azure CLI를 사용 하 여](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>참조

- [.NET 참조 용 저장소 클라이언트 라이브러리](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [파일 서비스 REST API 참조](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>블로그 게시물

- [Azure 파일 저장소 일반적으로 출시 되었습니다.](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [내부 Azure 파일 저장소](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [Microsoft Azure 파일 서비스 소개](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/05/12/introducing-microsoft-azure-file-service.aspx)
- [Microsoft Azure 파일에 대 한 영구 연결](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/05/27/persisting-connections-to-microsoft-azure-files.aspx)

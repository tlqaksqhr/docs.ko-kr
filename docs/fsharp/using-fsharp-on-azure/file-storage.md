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
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="749c4-104">F #을 사용 하 여 Azure 파일 저장소 시작</span><span class="sxs-lookup"><span data-stu-id="749c4-104">Get started with Azure File storage using F#</span></span> #

<span data-ttu-id="749c4-105">Azure 파일 저장소 파일 공유는 표준을 사용 하 여 클라우드를 제공 하는 서비스는 [서버 메시지 블록 (SMB) 프로토콜](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-105">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="749c4-106">SMB 2.1과 SMB 3.0을 둘 다 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-106">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="749c4-107">Azure 파일 저장소를 신속 하 고 비용이 많이 드는 다시 작성 하지 않고 Azure에 파일 공유를 사용 하는 레거시 응용 프로그램을 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-107">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="749c4-108">Azure 가상 컴퓨터 또는 클라우드 서비스 또는 온-프레미스 클라이언트에서 실행 중인 응용 프로그램 일반적인 SMB 공유를 탑재 하는 데스크톱 응용 프로그램 처럼 클라우드에서 파일 공유를 탑재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-108">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="749c4-109">응용 프로그램 구성 요소를 개수에 관계 없이 다음 탑재 하 고 수 파일 저장소 공유에 동시에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-109">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="749c4-110">파일 저장소의 개념적인 개요를 참조 하십시오 [파일 저장소에 대 한.NET 가이드](/azure/storage/storage-dotnet-how-to-use-files)합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-110">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="749c4-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="749c4-111">Prerequisites</span></span>

<span data-ttu-id="749c4-112">이 가이드를 사용 하려면 먼저 [Azure 저장소 계정 만들기](/azure/storage/storage-create-storage-account)합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="749c4-113">또한이 계정에 대 한 저장소 액세스 키를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-113">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="749c4-114">만들기는 F # 스크립트와 시작 F # 대화형</span><span class="sxs-lookup"><span data-stu-id="749c4-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="749c4-115">이 문서에 있는 예제에서 F # 응용 프로그램 또는 F # 스크립트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="749c4-116">F # 스크립트를 만들려면으로 파일 만들기는 `.fsx` 예를 들어 확장 `files.fsx`, F # 개발 환경에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-116">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="749c4-117">를 사용 하 여 한 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 를 설치 하는 `WindowsAzure.Storage` 패키지와 참조 `WindowsAzure.Storage.dll` 는 를사용하여스크립트에서`#r`지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="749c4-118">네임 스페이스 선언을 추가합니다</span><span class="sxs-lookup"><span data-stu-id="749c4-118">Add namespace declarations</span></span>

<span data-ttu-id="749c4-119">다음 추가 `open` 문을의 맨 위에 `files.fsx` 파일:</span><span class="sxs-lookup"><span data-stu-id="749c4-119">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="749c4-120">연결 문자열 가져오기</span><span class="sxs-lookup"><span data-stu-id="749c4-120">Get your connection string</span></span>

<span data-ttu-id="749c4-121">이 자습서에 대 한 Azure 저장소 연결 문자열이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-121">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="749c4-122">연결 문자열에 대 한 자세한 내용은 참조 [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="749c4-123">자습서에서는 다음과 같이 스크립트에 연결 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-123">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="749c4-124">그러나이 방법은 **좋지** 를 실제 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="749c4-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="749c4-125">저장소 계정 키 저장소 계정에 대 한 루트 암호와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="749c4-126">항상 저장소 계정 키를 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="749c4-127">하드 코딩을 다른 사용자에 게 액세스가 허용 되는 일반 텍스트 파일에 저장 하거나 다른 사용자에 게 배포 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="749c4-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="749c4-128">노출 되었다고 판단 되 면 Azure 포털을 사용 하 여 키를 다시 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="749c4-129">실제 응용 프로그램 저장소 연결 문자열을 유지 관리 하는 가장 좋은 방법은 구성 파일에는 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="749c4-130">구성 파일에서 연결 문자열을 페치 하려면이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="749c4-131">Azure 구성 관리자를 사용 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="749c4-132">.NET Framework 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="749c4-133">연결 문자열을 구문 분석</span><span class="sxs-lookup"><span data-stu-id="749c4-133">Parse the connection string</span></span>

<span data-ttu-id="749c4-134">연결 문자열을 구문 분석 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-134">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="749c4-135">이 반환 됩니다는 `CloudStorageAccount`합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-135">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="749c4-136">파일 서비스 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="749c4-136">Create the File service client</span></span>

<span data-ttu-id="749c4-137">`CloudFileClient` 유형을 프로그래밍 방식으로 파일 저장소에 저장 된 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-137">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="749c4-138">서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-138">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="749c4-139">이제 데이터를 읽고 데이터 파일 저장소를 기록 하는 코드를 작성할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-139">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="749c4-140">파일 공유 만들기</span><span class="sxs-lookup"><span data-stu-id="749c4-140">Create a file share</span></span>

<span data-ttu-id="749c4-141">이 예제에는 아직 없는 경우 파일 공유를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-141">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="749c4-142">루트 디렉터리 및 하위 디렉터리 만들기</span><span class="sxs-lookup"><span data-stu-id="749c4-142">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="749c4-143">루트 디렉터리를 가져올 여기에서 가져오고, 루트의 하위 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-143">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="749c4-144">아직 없는 경우 모두 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-144">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="749c4-145">텍스트 파일로 업로드</span><span class="sxs-lookup"><span data-stu-id="749c4-145">Upload text as a file</span></span>

<span data-ttu-id="749c4-146">이 예제에서는 텍스트 파일을 업로드 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-146">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="749c4-147">파일 파일의 로컬 복사본을 다운로드</span><span class="sxs-lookup"><span data-stu-id="749c4-147">Download a file to a local copy of the file</span></span>

<span data-ttu-id="749c4-148">여기 파일을 다운로드 하 여 방금 만든 로컬 파일에 내용을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-148">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="749c4-149">파일 공유에 대 한 최대 크기 설정</span><span class="sxs-lookup"><span data-stu-id="749c4-149">Set the maximum size for a file share</span></span>

<span data-ttu-id="749c4-150">아래 예제에는 공유에 대 한 현재 사용량을 확인 하는 방법과 공유에 대 한 할당량을 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-150">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="749c4-151">`FetchAttributes`호출 하는 공유의 채우기 `Properties`, 및 `SetProperties` Azure 파일 저장소에 로컬 변경 내용을 전파 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-151">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="749c4-152">파일 또는 파일 공유에 대 한 공유 액세스 서명 생성</span><span class="sxs-lookup"><span data-stu-id="749c4-152">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="749c4-153">파일 공유 또는 개별 파일에 대 한 공유 액세스 서명 (SAS)를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-153">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="749c4-154">또한 공유 액세스 서명을 관리 파일 공유에는 공유 액세스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-154">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="749c4-155">공유 액세스 정책 만들기 좋습니다 해야 손상 되 면 SAS를 해지 하는 수단을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-155">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="749c4-156">공유를 만들면 여기에서 정책을 공유에 액세스 하 고 다음 해당 정책을 사용 하 여 파일 공유에 대 한 SAS에 대 한 제약 조건을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-156">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="749c4-157">만들기 및 공유 액세스 서명을 사용 하는 방법에 대 한 자세한 내용은 참조 [를 사용 하 여 공유 액세스 서명 (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) 및 [만들고 사용 하 여 Blob 저장소 SAS](/azure/storage/storage-dotnet-shared-access-signature-part-2)합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-157">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="749c4-158">파일 복사</span><span class="sxs-lookup"><span data-stu-id="749c4-158">Copy files</span></span>

<span data-ttu-id="749c4-159">파일에 파일을 다른 파일이 나 blob 또는 blob에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-159">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="749c4-160">파일 또는 blob에 파일을 blob를 복사 하는 경우 있습니다 *해야* 동일한 저장소 계정 내에서 복사 하는 경우에 원본 개체를 인증 하는 공유 액세스 서명 (SAS)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-160">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="749c4-161">다른 파일에 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-161">Copy a file to another file</span></span>

<span data-ttu-id="749c4-162">여기에서 다른 파일 공유와 같은 공유에 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-162">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="749c4-163">이 복사 작업은 동일한 저장소 계정에서 파일 간 복사를 하기 때문에 복사 하려면 공유 키 인증을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-163">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="749c4-164">Blob에 파일을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-164">Copy a file to a blob</span></span>

<span data-ttu-id="749c4-165">파일을 만들면 여기서 동일한 저장소 계정 내에서 blob에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-165">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="749c4-166">복사 작업 중 소스 파일에 대 한 액세스를 인증 하는 서비스를 사용 하 여 소스 파일에 대 한 SAS를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-166">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="749c4-167">파일에 동일한 방법으로 blob을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-167">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="749c4-168">소스 개체가 blob 인 경우에 복사 작업 중 해당 blob에 대 한 액세스를 인증 하는 SAS를 생성 하십시오.</span><span class="sxs-lookup"><span data-stu-id="749c4-168">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="749c4-169">파일 저장소 메트릭을 사용 하 여 문제 해결</span><span class="sxs-lookup"><span data-stu-id="749c4-169">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="749c4-170">Azure 저장소 분석 파일 저장소에 대 한 메트릭을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-170">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="749c4-171">메트릭 데이터를 요청을 추적 하 고 문제를 진단 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-171">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="749c4-172">파일 저장소에 대 한 메트릭을 사용 하도록 설정할 수는 [Azure 포털](https://portal.azure.com), 다음과 같이 F #에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-172">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="749c4-173">다음 단계</span><span class="sxs-lookup"><span data-stu-id="749c4-173">Next steps</span></span>

<span data-ttu-id="749c4-174">Azure 파일 저장소에 대 한 자세한 내용은 다음이 링크를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-174">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="749c4-175">개념 문서 및 비디오</span><span class="sxs-lookup"><span data-stu-id="749c4-175">Conceptual articles and videos</span></span>

- [<span data-ttu-id="749c4-176">Azure 파일 저장소: 개설 클라우드 Windows 및 Linux 용 SMB 파일 시스템</span><span class="sxs-lookup"><span data-stu-id="749c4-176">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="749c4-177">Linux에서 Azure 파일 저장소를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="749c4-177">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="749c4-178">도구 파일 저장소에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="749c4-178">Tooling support for File storage</span></span>

- [<span data-ttu-id="749c4-179">Azure 저장소에서 Azure PowerShell을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="749c4-179">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="749c4-180">Microsoft Azure 저장소와 AzCopy를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="749c4-180">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="749c4-181">Azure 저장소와 Azure CLI를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="749c4-181">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="749c4-182">참조</span><span class="sxs-lookup"><span data-stu-id="749c4-182">Reference</span></span>

- [<span data-ttu-id="749c4-183">.NET 참조 용 저장소 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="749c4-183">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="749c4-184">파일 서비스 REST API 참조</span><span class="sxs-lookup"><span data-stu-id="749c4-184">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="749c4-185">블로그 게시물</span><span class="sxs-lookup"><span data-stu-id="749c4-185">Blog posts</span></span>

- [<span data-ttu-id="749c4-186">Azure 파일 저장소 일반적으로 출시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="749c4-186">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="749c4-187">내부 Azure 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="749c4-187">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [<span data-ttu-id="749c4-188">Microsoft Azure 파일 서비스 소개</span><span class="sxs-lookup"><span data-stu-id="749c4-188">Introducing Microsoft Azure File Service</span></span>](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/05/12/introducing-microsoft-azure-file-service.aspx)
- [<span data-ttu-id="749c4-189">Microsoft Azure 파일에 대 한 영구 연결</span><span class="sxs-lookup"><span data-stu-id="749c4-189">Persisting connections to Microsoft Azure Files</span></span>](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/05/27/persisting-connections-to-microsoft-azure-files.aspx)

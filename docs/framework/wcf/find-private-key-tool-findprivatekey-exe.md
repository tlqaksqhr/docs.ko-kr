---
title: "개인 키 찾기 도구(FindPrivateKey.exe)"
ms.date: 09/11/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d515077106b8f0527d045d5ef7fb6d7c0c7aa62
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="46975-102">개인 키 찾기 도구(FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="46975-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="46975-103">이 명령줄 도구는 인증서 저장소에서 개인 키를 검색하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46975-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="46975-104">예를 들어 *FindPrivateKey.exe* 인증서 저장소에서 특정 X.509 인증서와 연결 된 개인 키 파일의 이름과 위치를 찾는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46975-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46975-105">FindPrivateKey 도구는 WCF 샘플로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="46975-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="46975-106">이 샘플을 찾을 수 있는 위치 및 빌드 방법에 대 한 자세한 내용은 참조 하십시오. [FindPrivateKey](./samples/findprivatekey.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="46975-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="46975-107">구문</span><span class="sxs-lookup"><span data-stu-id="46975-107">Syntax</span></span>

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="46975-108">설명</span><span class="sxs-lookup"><span data-stu-id="46975-108">Remarks</span></span>

<span data-ttu-id="46975-109">다음 표에서는 개인 키 찾기 도구(FindPrivateKey.exe)와 함께 사용할 수 있는 인수 및 옵션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="46975-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="46975-110">인수</span><span class="sxs-lookup"><span data-stu-id="46975-110">Argument</span></span>|<span data-ttu-id="46975-111">설명</span><span class="sxs-lookup"><span data-stu-id="46975-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="46975-112">인증서 저장소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="46975-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="46975-113">인증서 저장소의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="46975-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="46975-114">옵션</span><span class="sxs-lookup"><span data-stu-id="46975-114">Option</span></span>|<span data-ttu-id="46975-115">설명</span><span class="sxs-lookup"><span data-stu-id="46975-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="46975-116">`/n <`*subjectName*`>`</span><span class="sxs-lookup"><span data-stu-id="46975-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="46975-117">인증서의 주체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46975-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="46975-118">`/t <`*지문*`>`</span><span class="sxs-lookup"><span data-stu-id="46975-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="46975-119">인증서의 지문을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46975-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="46975-120">인증서의 지문을 검색하려면 Certmgr.exe를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46975-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="46975-121">파일 이름만 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="46975-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="46975-122">디렉터리만 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="46975-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="46975-123">절대 파일 이름을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="46975-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="46975-124">예제</span><span class="sxs-lookup"><span data-stu-id="46975-124">Examples</span></span>

<span data-ttu-id="46975-125">다음 명령은 John Doe에 대 한 개인 키를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="46975-125">The following command retrieves the private key for John Doe:</span></span>

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="46975-126">다음 명령은 로컬 컴퓨터에 대 한 개인 키를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="46975-126">The following command retrieves the private key for the local machine:</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```
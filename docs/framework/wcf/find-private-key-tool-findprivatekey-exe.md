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
ms.workload: dotnet
ms.openlocfilehash: 4bdfa1a9e45332e8c2acbbc8cd8a09bd2f927fbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a>개인 키 찾기 도구(FindPrivateKey.exe)

이 명령줄 도구는 인증서 저장소에서 개인 키를 검색하는 데 사용할 수 있습니다. 예를 들어 *FindPrivateKey.exe* 인증서 저장소에서 특정 X.509 인증서와 연결 된 개인 키 파일의 이름과 위치를 찾는 데 사용할 수 있습니다.

> [!IMPORTANT]
> FindPrivateKey 도구는 WCF 샘플로 제공됩니다. 이 샘플을 찾을 수 있는 위치 및 빌드 방법에 대 한 자세한 내용은 참조 하십시오. [FindPrivateKey](./samples/findprivatekey.md)합니다.

## <a name="syntax"></a>구문

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a>설명

다음 표에서는 개인 키 찾기 도구(FindPrivateKey.exe)와 함께 사용할 수 있는 인수 및 옵션을 설명합니다.

|인수|설명|
|--------------|-----------------|
|`storeName`|인증서 저장소의 이름입니다.|
|`storeLocation`|인증서 저장소의 위치입니다.|

|옵션|설명|
|------------|-----------------|
|`/n <`*subjectName*`>`|인증서의 주체 이름을 지정합니다.|
|`/t <`*지문*`>`|인증서의 지문을 지정합니다. 인증서의 지문을 검색하려면 Certmgr.exe를 사용합니다.|
|`/f`|파일 이름만 출력합니다.|
|`/d`|디렉터리만 출력합니다.|
|`/a`|절대 파일 이름을 출력합니다.|

## <a name="examples"></a>예제

다음 명령은 John Doe에 대 한 개인 키를 검색합니다.

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

다음 명령은 로컬 컴퓨터에 대 한 개인 키를 검색합니다.

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```
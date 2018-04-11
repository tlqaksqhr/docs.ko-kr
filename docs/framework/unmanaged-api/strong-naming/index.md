---
title: 강력한 이름 지정(관리되지 않는 API 참조)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ce89e27089ea2f0c918d0fe37c4eea141698f9be
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="strong-naming-unmanaged-api-reference"></a>강력한 이름 지정(관리되지 않는 API 참조)
강력한 이름 API에는 클라이언트를를 강력한 이름 어셈블리에 대 한 서명을 관리할 수 있습니다.  
  
 강력한 이름을 사용하여 어셈블리에 서명하면 어셈블리 매니페스트를 포함하는 파일에 공개 키 암호화가 추가됩니다. 강력한 이름 서명을 사용 하면 이름 고유성 이름 스푸핑을 방지 하 고 참조를 확인할 때 고유 id를 가진 호출자에 게 제공 합니다. 그러나 신뢰 되지 수준은 강력한 이름으로 연결 됩니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [강력한 이름 지정 전역 정적 함수](http://msdn.microsoft.com/library/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)  
 강력한 이름 API를 사용 하는 관리 되지 않는 전역 정적 함수를 설명 합니다.  
  
> [!NOTE]
>  이러한 함수의 모든 사용이 중단 된 부터는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다. 제안 된 대안에 대 한 참조는 [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) 인터페이스입니다.  
  
 [GetHashFromAssemblyFile 함수](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 지정된 된 해시 알고리즘을 사용 하 여 지정 된 어셈블리 파일의 해시를 가져옵니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [GetHashFromAssemblyFileW 함수](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 지정 된 해시 알고리즘을 사용 하는 유니코드 문자열로 지정 된 어셈블리 파일의 해시를 가져옵니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [GetHashFromBlob 함수](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 지정된 된 해시 알고리즘을 사용 하 여 지정 된 메모리 주소에서 어셈블리의 해시를 가져옵니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [GetHashFromFile 함수](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 지정된 된 파일의 내용에 대 한 해시를 생성 합니다.  부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [GetHashFromFileW 함수](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 유니코드 문자열에 의해 지정 된 파일의 내용에 대 한 해시를 생성 합니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [GetHashFromHandle 함수](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 지정된 된 해시 알고리즘을 사용 하 여 지정 된 파일 핸들을 사용 하 여 파일의 내용에 대 한 해시를 생성 합니다.  부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameCompareAssemblies 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 두 어셈블리가 강력한 이름 서명만 다른 지 여부를 결정 합니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameErrorInfo 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 강력한 이름 함수 중 하나에서 발생 하는 마지막 오류 코드를 가져옵니다.  
  
 [StrongNameFreeBuffer 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 와 같은 강력한 이름 함수에 대 한 이전 호출을 사용 하 여 할당 된 메모리를 확보 [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), 또는 [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).   부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameGetBlob 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 지정된 된 주소에서 실행 파일의 이진 표현으로 지정된 된 버퍼를 채웁니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameGetBlobFromImage 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 지정 된 메모리 주소에서 어셈블리 이미지의 이진 표현을 가져옵니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameGetPublicKey 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 개인/공개 키 쌍에서 공개 키를 가져옵니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameHashSize 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 지정된 된 해시 알고리즘을 사용 하 여 해시에 필요한 버퍼 크기를 가져옵니다.  부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameKeyDelete 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 지정된 된 키 컨테이너를 삭제합니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameKeyGen 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 강력한 이름 사용 하기 위해 새 공개/개인 키 쌍을 만듭니다.  부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameKeyGenEx 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 강력한 이름 사용 하기 위해 지정된 된 키 크기와 새 공개/개인 키 쌍을 생성합니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameKeyInstall 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 컨테이너에 공개/개인 키 쌍을 가져옵니다.  부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameSignatureGeneration 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 지정된 된 어셈블리에 대 한 강력한 이름 서명을 생성합니다.   부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameSignatureGenerationEx 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 지정된 된 플래그에 따라 지정된 된 어셈블리에 대 한 강력한 이름 서명을 생성 합니다.    부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameSignatureSize 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 강력한 이름 서명의 크기를 반환 합니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameSignatureVerification 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 어셈블리 매니페스트에 제공 된 경로의 강한 이름 서명을 확인 하도록 지정된 된 플래그에 따라 포함 되는지 여부를 나타내는 값을 가져옵니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameSignatureVerificationEx 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 제공 된 경로의 어셈블리 매니페스트는 강력한 이름 서명을 포함 되는지 여부를 나타내는 값을 가져옵니다.  부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameSignatureVerificationFromImage 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 연결된 된 공개 키가 이미 메모리에 매핑되어 있는 어셈블리가 올바른지 확인 합니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameTokenFromAssembly 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 지정한 어셈블리 파일에서 강력한 이름 토큰을 만듭니다.  부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameTokenFromAssemblyEx 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 지정 된 어셈블리 파일에서 강력한 이름 토큰을 만들고 공개 키를 반환 합니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StrongNameTokenFromPublicKey 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 공개 키를 나타내는 토큰을 가져옵니다. 부터 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [강력한 이름 지정 구조](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)  
 강력한 이름 어셈블리에 대 한 서명을 관리 하는 강력한 이름 API를 사용 하는 관리 되지 않는 구조를 설명...  
  
 [PublicKeyBlob 구조체](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 이진 형식에 공개/개인 키 쌍의 공개 키를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [관리되지 않는 API 참조](../../../../docs/framework/unmanaged-api/index.md)

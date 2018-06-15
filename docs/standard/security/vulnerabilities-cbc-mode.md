---
title: 타이밍 ֳ 패딩을 사용 하 여 CBC 모드 대칭 암호 해독
description: 검색 및 패딩을 사용 하 여 암호 블록 체인 (CBC) 모드 대칭 해독 된 타이밍 취약성을 완화 하는 방법에 알아봅니다.
ms.date: 06/12/2018
author: blowdart
ms.author: mairaw
ms.openlocfilehash: a07acbb943c430f6e26bec44f55a5c84306da513
ms.sourcegitcommit: 73a662360bbe2f43c19aca1fbcc2565025c60cd8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2018
ms.locfileid: "35327460"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a>타이밍 ֳ 패딩을 사용 하 여 CBC 모드 대칭 암호 해독

현재 알려진된 암호화 연구에 따라 Microsoft 있다고 인식 하는 매우 특정 한 상황을 제외 하 고는 더 이상 확인할 수 있는 안쪽 여백 되었을 때 대칭 암호화의 암호 블록 체인 (CBC) 모드를 사용 하 여 암호화 된 데이터를 해독 하는 안전 암호 텍스트의 무결성을 확인 하지 않고 적용 합니다.

## <a name="introduction"></a>소개

패딩 oracle 공격에 키를 알 필요 없이 데이터의 내용을 해독 하도록 허용 하는 암호화 된 데이터에 대 한 공격의 형식입니다.

Oracle에는 "알릴"을 실행 하는 작업 올바른 인지 여부에 대 한 공격자가 정보가 제공 참조 합니다. 스 보드 재생 다음과 같이 가정해 봅니다 또는 자식이 있는 게임 카드입니다. 때 그녀의 얼굴 켜지는 큰 웃는 얼굴와 그녀는 그녀가 생각 하기 때문에 이동 하려면 빈 좋은 oracle를 확인 하려고 합니다. 는 상대도 사용할 수 있습니다이 oracle 다음 이사를 적절 하 게 계획 합니다.

안쪽 여백은 특정 암호화 용어입니다. 일부 암호화는 데이터를 암호화 하는 데 사용 되는 알고리즘은 각 블록의 크기가 고정된 되어 있는 데이터 블록에서 작동 합니다. 데이터를 암호화 하려는 올바른 크기는 블록에 맞게 없다면 완료 될 때까지 데이터 채워집니다. 다양 한 형식의 안쪽 여백에는 항상 있어야 하는 원래 입력 올바른 크기의 경우에 해당 패딩이 필요 합니다. 따라서 항상 안전 하 게 제거할 암호 해독 시 안쪽 여백 수 있습니다.

다음 두 가지를 함께 배치 패딩 oracle 소프트웨어 구현을 암호 해독 된 데이터에 유효한 안쪽 여백에 있는지 여부를 알 수 있습니다. Oracle 같은 간단한 "잘못 된 패딩" 라고 표시 하는 값을 반환 하거나 조금 더 복잡 한 눈에 띄게 다른 시간 잘못 된 블록이 아닌 유효한 블록을 처리 하는 것과 같은 수 있습니다.

암호 블록 기반 다른 이라는 속성을, 두 번째 블록에 있는 데이터의 첫 번째 블록에 데이터의 관계를 결정 하는 모드 등에입니다. CBC는 가장 자주 사용 되는 모드 중 하나입니다. CBC로는 IV (Initialization Vector), 알려진 초기 임의 블록을 정의 하 고 동일한 키가 있는 동일한 메시지를 암호화 하지 않습니다 항상 생성 되는 동일한 암호화 된 출력 하기 위해 정적 암호화의 결과 함께 이전 블록을 결합 합니다.

공격자가 CBC 데이터가 구조화 되는 방식을 함께에서 패딩 oracle, צ ְ ײ, oracle를 노출 하는 코드를 약간 변경 된 메시지를 보내고 oracle ¿ë à ú 될 때까지 데이터를 보내는 유지 데이터가 올바른지 합니다. 이 응답에서 공격자는 바이트 단위로 메시지를 해독할 수 있습니다.

최신 컴퓨터 네트워크는 이러한 높은 품질 공격자 매우 작은 (0.1 밀리초 미만) 원격 시스템에서 실행의 차이점에에서 시간을 검색할 수 있습니다. 데이터가 변조 되지 않은 경우 성공적으로 암호 해독만 발생할 수 있음을 가정 하는 응용 프로그램 성공 하거나 실패 한 암호 해독의 차이 관찰 하도록 설계 된 도구에서 공격에 취약할 수 있습니다. 이러한 시간 차이로 다른 항목 보다 일부 언어 또는 라이브러리에서 더 큰 수 있지만, 이제 믿고는 모든 언어 및 라이브러리에 대 한 유용한 위협 경우에 응용 프로그램의 오류에 대응 고려 됩니다.

이 공격 암호화 된 데이터를 변경 하 고는 oracle 결과 테스트할 수 있는 기능에 의존 합니다. 완전히 방지할 수 있었던 공격을 완화 하는 유일한 방법은 암호화 된 데이터의 변경 내용을 감지 하 여 모든 작업을 실행 하지 않습니다. 이 작업을 수행 하는 표준 방법은 데이터에 대 한 서명을 만드는 모든 작업을 수행 하기 전에 해당 서명 유효성 검사를 하는 것입니다. 서명이 확인할 수 있어야 합니다., 공격자가 만들 수 없습니다, 그리고 그렇지 않으면 암호화 된 데이터를 변경할 것 다음 변경 된 데이터를 기반으로 새 서명을 계산 합니다. 한 가지 일반적인 유형의 적절 한 서명이 키 지정 해시 메시지 인증 코드 (HMAC) 라고 합니다. HMAC 걸리는 비밀 키 HMAC를 생성 하는 사람에만 하 고 유효성을 검사 하는 사람에 알려진 점에서 체크섬과 다릅니다. 키를 소유한 없이 올바른 HMAC를 생성할 수 없습니다. 데이터를 받으면 암호화 된 데이터를 독립적으로 계산 하지 비밀 키를 사용 하 여 HMAC 하는 보낸 사람에 게 공유 힙이고 있습니다를 보낸 것에 대해 HMAC를 계산 하는 비교 하 합니다. 이 비교 상수 시간 이어야 합니다., 그렇지 않으면 사용자가 추가한 다른 감지 oracle 다른 종류의 공격을 허용 합니다.

요약 하자면, 사용 하는 CBC 블록 암호화를 안전 하 게 패딩, HMAC (또는 다른 데이터 무결성 검사) 시도 하기 전에 분할 된 시간 비교를 사용 하 여 데이터를 암호 해독의 유효성을 검사 하는 결합 해야 합니다. 이후 변경 된 모든 메시지에 응답을 생성 하기 위해 동일한 양 시간이 걸릴 수 있었던 공격 금지 됩니다.

## <a name="who-is-vulnerable"></a>취약 한 누구 입니까

이 취약성 자체 암호화 및 암호 해독을 수행 하 고 있는 관리 및 네이티브 응용 프로그램에 적용 됩니다. 이 예를 들어:

- 서버에서 이상 암호 해독에 대 한 쿠키를 암호화 하는 응용 프로그램입니다.
- 열이 있는 테이블에 데이터를 삽입 하는 사용자에 대 한 기능을 제공 하는 데이터베이스 응용 프로그램을 나중에 암호 해독 됩니다.
- 데이터 전송 중에 데이터를 보호 하는 공유 키를 사용 하 여 암호화를 사용 하는 응용 프로그램을 전송 합니다.
- 암호화 하 고 "내부" TLS 터널 메시지를 해독 하는 응용 프로그램입니다.

단독 TLS를 사용 하 여 수 보호할 수 없으며 이러한 시나리오에서 참고 합니다.

취약 한 응용 프로그램:

- CBC 암호화 모드를 사용 하 여 PKCS #7 또는 ANSI X.923 같은 확인할 수 있는 안쪽 여백 모드에서 데이터를 해독 합니다.
- MAC 또는 비대칭는 디지털 서명) (통해 데이터 무결성 검사를 수행할 필요 없이 암호 해독을 수행 합니다.

암호화 메시지 구문 (PKCS #7/CMS) EnvelopedData 구조와 같은 이러한 기본 형식 맨 위에 추상화를 기반으로 빌드된 응용 프로그램에도 적용 됩니다.

## <a name="related-areas-of-concern"></a>관련된 문제 영역을

Research는 ISO 10126에 해당 하는 메시지에는 잘 알려진 또는 예측 가능한 바닥글 구조 때 패딩 채워져 CBC 메시지에 대 한 추가 문제는 그리 Microsoft 졌 합니다. W3C XML 암호화 구문 및 처리 권장 사항 (xmlenc EncryptedXml)의 규칙을 따를 준비 된 콘텐츠 예를 들어입니다. W3C 지침을 암호화 한 다음 메시지에 서명 된 시간에 적절 한 고려 되었지만, 이제 좋습니다 항상 암호화 then-기호 (+)를 수행 하 합니다.

비대칭 키와 임의의 메시지 간의 내재 된 트러스트 관계가 없는 없기 때문에 항상 응용 프로그램 개발자는 비대칭 서명 키의 적용 여부를 확인 하는 중에 주의 이어야 합니다.

## <a name="details"></a>설명

지금까지 암호화 및 중요 한 데이터를 HMAC 또는 RSA 서명 등의 방법을 사용 하 여 인증 해야 합의 되었습니다. 그러나 암호화 및 인증 작업을 시퀀싱 하는 방법에 대 한 명확한 지침 덜 되었습니다. 이 문서에 자세히 설명 하는 취약점으로 인해 Microsoft의 지침이 되었습니다 항상 "암호화 then-기호" 패러다임을 사용 합니다. 즉, 먼저 대칭 키를 사용 하 여 데이터를 암호화 한 다음 암호 텍스트 (암호화 된 데이터)을 통해 MAC 또는 비대칭 서명 계산 합니다. 데이터의 암호를 해독 하는 경우에 반대로 수행 합니다. 먼저, MAC 또는 암호화, 서명 확인 다음 암호를 해독 합니다.

"Oracle 공격 패딩" 것으로 알려져 10 년에 대 한 알려진 취약점의 클래스입니다. 이러한 취약점 4096 개 이하의 시도/데이터 블록을 사용 하 여 AES 및 3DES, 같은 대칭 블록 알고리즘으로 암호화 된 데이터를 해독 하는 공격자가 있습니다. 이러한 취약점 확인 사용 하 여 암호를 차단 하는 팩트의 끝에 패딩 확인할 수 있는 데이터와 함께 가장 자주 사용 됩니다. 공격자가 암호화 텍스트를 변조할 수 있고 확인 여부는 변조 끝에 패딩의 형식에 오류가 발생, 있는 경우 공격자가 데이터를 해독할 수를 찾을 수 있습니다.

서비스에서 반환 되는 패딩 ASP.NET 취약점 같은 유효 했는지 여부에 따라 서로 다른 오류 코드에 기반한 실용적인 공격 처음에 [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx)합니다. 그러나 Microsoft 타이밍 처리 유효 하지 않은 패딩의에서 차이 만큼만 사용 하 여 비슷한 공격을 수행할 실용적이 이제가 있습니다.

정보를 표시 하지 않고 데이터 무결성을 확인할 수는 서명을 사용 하는 암호화 체계 권한과 (관계 없이 내용)는 데이터의 지정 된 길이 대 한 고정 런타임과 서명 확인이 수행 하는 통해 공격자는 [쪽 채널](https://en.wikipedia.org/wiki/Side-channel_attack)합니다. 무결성 검사가 변조 된 모든 메시지를 거부 하는 이후 안쪽 여백 oracle 위협 완화 됩니다.

## <a name="guidance"></a>지침

무엇 보다도, 모든 데이터 또는 기밀 있는 필요를 통해 보안 TLS (전송 계층), 후속 Secure Sockets Layer (SSL)를 전송 될 것이 좋습니다.

다음으로 응용 프로그램을 분석:

- 수행 하는 어떤 암호화 정확 하 게 이해 하 고 플랫폼 및 Api를 사용 하는에서 제공 되 고 어떤 암호화 키를 누릅니다.
- 확신할 수은 대칭의 각 계층에서 각 사용 [블록 암호화 알고리즘](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)AES 및 3DES CBC 모드에서 비밀 키가 지정 된 데이터 무결성 검사를 사용 하는 통합 등 (프로그램 비대칭 서명은 HMAC 암호화 모드를 변경 하려면 [암호화 인증](https://en.wikipedia.org/wiki/Authenticated_encryption) GCM 등 CCM (AE) 모드).

현재 조사 결과에 따라, 일반적으로 믿고 비 AE 모드 암호화에 대 한 인증 및 암호화 단계가 독립적으로 수행 됩니다 때 인증 암호 텍스트 (암호화-then-기호) 임을 일반 수 있는 최상의 옵션입니다. 그러나 암호화를 일괄적으로 적용할 올바른 응답이 없습니다 및이 일반화 전문 cryptographer에서 최적의 상태로 방향이 지정 된 도움말 제공 되지 않습니다.

인증 되지 않은 CBC 암호 해독을 수행 하지만 해당 메시징 형식을 변경할 수 없는 응용 프로그램이 같은 완화를 통합 하려고 하도록 합니다.

- 확인 하거나 안쪽 여백을 제거 하려면 암호 해독기를 허용 하지 않고 암호 해독:
  - 적용 된 채움을 여전히 제거 / 무시 해야, 응용 프로그램에 부담을 이동 하 합니다.
  - 기능은 다른 응용 프로그램 데이터 확인 논리에 안쪽 여백 확인 및 제거를 통합할 수 있습니다. 일정 한 시간에 안쪽 여백 확인 및 데이터 확인 작업을 수행할 수 있습니다, 위협을 줄어듭니다.
  - 안쪽 여백의 해석은 변경 인식된 메시지 길이, 이후 있을 수 있습니다이 방법에서 발생 하는 타이밍 정보입니다.
- I s o 10126를 암호 해독 패딩 모드를 변경 합니다.
  - I s o 10126 암호 해독 패딩은 PKCS7 암호화 패딩입니다 및 ANSIX923 암호화 패딩입니다 모두와 호환 됩니다.
  - 모드를 변경 하면이 안쪽 여백 oracle 기술을 전체 블록 대신 1 바이트를 줄입니다. 그러나 콘텐츠를 닫기 XML 요소 등의 잘 알려진 바닥글 경우 관련된 공격 메시지의 나머지 공격을 계속할 수 있습니다.
  - 또한이 경우 공격자가 서로 다른 메시지 오프셋으로 여러 번 암호화 될 수 동일한 일반 강제 변환할 수에 일반 텍스트 복구를 하지 하지 않습니다.
- 게이트 타이밍 신호를 완화 시킬 암호 해독 호출의 평가:
  - 보류 시간 계산에 시간 안쪽 여백을 포함 된 모든 데이터 세그먼트 데 소요 되는 암호 해독 작업의 최대 크기를 초과 하는 최소가 있어야 합니다.
  - 제공 된 지침에 따라 시간 계산을 수행 해야 [고해상도 타임 스탬프를 가져오는](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx)를 사용 하 여 <xref:System.Environment.TickCount?displayProperty=nameWithType> (오버플로 롤 over /)에 따라 나 빼기 (NTP 조정에 따라 두 개의 시스템 타임 스탬프 오류)입니다.
  - 시간 계산 관리 되어야 합니다. 암호 해독 작업의 모든 잠재적 예외를 포함 하 여 포함 또는 c + + 응용 프로그램 뿐 아니라 끝에 패딩 합니다.
  - 성공 또는 실패 확인 된 경우에 아직, 타이밍 게이트를 만료 될 때 오류를 반환 해야 합니다.
- 인증 되지 않은 암호 해독을 수행 하는 서비스 모니터링을 통해 "잘못 된" 메시지의 양이 했음을 감지 하는 기능이 있어야 합니다.
  - 이 신호 (합법적으로 손상 된 데이터) 거짓 긍정 및 거짓 부 정의 (공격을 탐지를 피하도록 충분히 긴 시간 동안 분배)를 전달 하는 것을 염두에 두십시오.

## <a name="finding-vulnerable-code---native-applications"></a>취약 한 코드-네이티브 응용 프로그램 찾기

Windows 암호화에 대해 작성 하는 프로그램에 대 한: 차세대 (CNG) 라이브러리:

- 암호 해독 호출이 [BCryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa375391.aspx)을 지정 하는 `BCRYPT_BLOCK_PADDING` 플래그입니다.
- 키 핸들 호출 하 여 활성화 되었습니다 [BCryptSetProperty](https://msdn.microsoft.com/library/windows/desktop/aa375504.aspx) 와 [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) 로 설정 `BCRYPT_CHAIN_MODE_CBC`합니다.
  - 이후 `BCRYPT_CHAIN_MODE_CBC` 은 기본값인 영향을 받는 코드에 대 한 모든 값 할당 되지 않을 수 있습니다 `BCRYPT_CHAINING_MODE`합니다.

이전 Windows 암호화 API에 대해 빌드된 프로그램:

- 암호 해독 호출이 [CryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa379913.aspx) 와 `Final=TRUE`합니다.
- 키 핸들 호출 하 여 활성화 되었습니다 [CryptSetKeyParam](https://msdn.microsoft.com/library/windows/desktop/aa380272.aspx) 와 [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) 로 설정 `CRYPT_MODE_CBC`합니다.
  - 이후 `CRYPT_MODE_CBC` 은 기본값인 영향을 받는 코드에 대 한 모든 값 할당 되지 않을 수 있습니다 `KP_MODE`합니다.

## <a name="finding-vulnerable-code---managed-applications"></a>취약 한 코드 찾기-관리 되는 응용 프로그램

- 암호 해독 호출 하는 것은 <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> 또는 <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> 에 대 한 메서드 <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>합니다.
  - 이.NET 내에서 다음 파생된 형식을 포함 되지만 타사 형식을 포함 될 수도 있습니다.
    - <xref:System.Security.Cryptography.Aes>
    - <xref:System.Security.Cryptography.AesCng>
    - <xref:System.Security.Cryptography.AesCryptoServiceProvider>
    - <xref:System.Security.Cryptography.AesManaged>
    - <xref:System.Security.Cryptography.DES>
    - <xref:System.Security.Cryptography.DESCryptoServiceProvider>
    - <xref:System.Security.Cryptography.RC2>
    - <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
    - <xref:System.Security.Cryptography.Rijndael>
    - <xref:System.Security.Cryptography.RijndaelManaged>
    - <xref:System.Security.Cryptography.TripleDES>
    - <xref:System.Security.Cryptography.TripleDESCng>
    - <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> 속성이로 설정 된 <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, 또는 <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>합니다.
  - 이후 <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> 은 기본값인 영향을 받는 코드 되지 할당 했는 <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> 속성입니다.
- <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> 속성이로 설정 된 <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType>
  - 이후 <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> 은 기본값인 영향을 받는 코드 되지 할당 했는 <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> 속성입니다.

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a>암호화 메시지 구문 취약 한 코드-찾기

암호화 된 내용이 AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), (1.3.14.3.2.7) DES, 3DES CBC 모드를 사용 하는 인증 되지 않은 CMS EnvelopedData 메시지 (1.2.840.113549.3.7) 또는 RC2 (1.2.840.113549.3.2)은 취약 한도 메시지 블록의 암호화 알고리즘을 사용 하 여 CBC 모드에서 합니다.

스트림 암호화가 문제에 취약 하지 않으면 동안 항상 ContentEncryptionAlgorithm 값 검사를 통해 데이터를 인증 하는 것이 좋습니다.

관리 되는 응용 프로그램에 대 한 blob 수 CMS EnvelopedData에 전달 되는 모든 값을 검색 <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>합니다.

네이티브 응용 프로그램에 대 한 CMS EnvelopedData blob를 검색할 수 있는 CMS 핸들을 통해에 지정 된 값으로 [CryptMsgUpdate](https://msdn.microsoft.com/library/windows/desktop/aa380231.aspx) 인 결과 [CMSG_TYPE_PARAM](https://msdn.microsoft.com/library/windows/desktop/aa380227.aspx) 은 `CMSG_ENVELOPED` CMS 핸들은 및/또는 나중에 보낸는 `CMSG_CTRL_DECRYPT` 명령을 통해 [CryptMsgControl](https://msdn.microsoft.com/library/windows/desktop/aa380220.aspx)합니다.

## <a name="vulnerable-code-example---managed"></a>취약 한 코드 예제에서는-관리

이 메서드는 쿠키를 읽고 해독과 데이터 무결성 검사 없이 표시 됩니다. 따라서이 방법으로 읽을 수 있는 쿠키의 내용이 받은 사람, 사용자 또는 암호화 된 쿠키 값은 확보 하는 모든 공격자가 공격 받을 수입니다.

```csharp
private byte[] DecryptCookie(string cookieName)
{
    HttpCookie cookie = Request.Cookies[cookieName];

    if (cookie == null)
    {
        return null;
    }

    using (ICryptoTransform decryptor = _aes.CreateDecryptor())
    using (MemoryStream memoryStream = new MemoryStream())
    using (CryptoStream cryptoStream =
        new CryptoStream(memoryStream, decryptor, CryptoStreamMode.Write))
    {
        byte[] readCookie = Convert.FromBase64String(cookie.Value);
        cryptoStream.Write(readCookie, 0, readCookie.Length);
        cryptoStream.FlushFinalBlock();
        return memoryStream.ToArray();
    }
}
```

## <a name="example-code-following-recommended-practices---managed"></a>예제 코드 다음 사례-관리 되는 것이 좋습니다.

다음 샘플 코드의 비표준 메시지 형식을 사용 하 여

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

여기서는 `cipher_algorithm_id` 및 `hmac_algorithm_id` 알고리즘 식별자는 해당 알고리즘의 로컬 응용 프로그램 (비표준) 표현입니다. 이러한 식별자 합리적 대신 기존 메시징 프로토콜의 다른 부분에 완전 연결된 bytestream으로입니다.

또한이 예제에서는 HMAC 키와 암호화 키를 파생 하는 단일 마스터 키를 사용 합니다. 이 기능을 하기 위해 두 키와 다른 값을 유지 하 고 이중 키가 지정 된 응용 프로그램에 단일 키가 지정 된 응용 프로그램에 대 한 편의 위해 둘 다 제공 됩니다. HMAC 키와 암호화 키 동기화 되지 않을 수 없습니다 자세한 보장 합니다.

이 샘플을 허용 하지 않습니다는 <xref:System.IO.Stream> 암호화 또는 암호 해독 합니다. 현재 데이터 형식을 사용 하면 단일 패스 암호화 어려운 때문에 `hmac_tag` 값 앞에 오는 암호 텍스트입니다. 그러나이 형식은 모든 고정 크기 요소 구문 분석기를 보다 간단 하 게에 유지 되기 때문에 선택 되었습니다. 이 데이터 형식으로 구현 자가 GetHashAndReset를 호출 하 고 TransformFinalBlock를 호출 하기 전에 결과 확인 하는 주의가 요구는 있지만 단일 패스 decrypt이 가능 합니다. 중요 한 스트리밍 암호화의 경우 서로 다른 AE 모드 필요할 수 있습니다.

```csharp
// ==++==
//
//   Copyright (c) Microsoft Corporation.  All rights reserved.
//
//   Shared under the terms of the Microsoft Public License,
//   https://opensource.org/licenses/MS-PL
//
// ==--==

using System;
using System.Diagnostics;
using System.IO;
using System.Runtime.CompilerServices;
using System.Security.Cryptography;

namespace Microsoft.Examples.Cryptography
{
    public enum AeCipher : byte
    {
        Unknown,
        Aes256CbcPkcs7,
    }

    public enum AeMac : byte
    {
        Unknown,
        HMACSHA256,
        HMACSHA384,
    }

    /// <summary>
    /// Provides extension methods to make HashAlgorithm look like .NET Core's
    /// IncrementalHash
    /// </summary>
    internal static class IncrementalHashExtensions
    {
        public static void AppendData(this HashAlgorithm hash, byte[] data)
        {
            hash.TransformBlock(data, 0, data.Length, null, 0);
        }

        public static void AppendData(
            this HashAlgorithm hash,
            byte[] data,
            int offset,
            int length)
        {
            hash.TransformBlock(data, offset, length, null, 0);
        }

        public static byte[] GetHashAndReset(this HashAlgorithm hash)
        {
            hash.TransformFinalBlock(Array.Empty<byte>(), 0, 0);
            return hash.Hash;
        }
    }

    public static partial class AuthenticatedEncryption
    {
        /// <summary>
        /// Use <paramref name="masterKey"/> to derive two keys (one cipher, one HMAC)
        /// to provide authenticated encryption for <paramref name="message"/>.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="message">The message to encrypt</param>
        /// <returns>
        /// A concatenation of
        /// [cipher algorithm+chainmode+padding][mac algorithm][authtag][IV][ciphertext],
        /// suitable to be passed to <see cref="Decrypt"/>.
        /// </returns>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or bigger) value generated
        /// by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>.
        /// This implementation chooses to block deficient inputs by length, but does not
        /// make any attempt at discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase)
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Encrypt(byte[] masterKey, byte[] message)
        {
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (message == null)
                throw new ArgumentNullException(nameof(message));

            // First, choose an encryption scheme.
            AeCipher aeCipher = AeCipher.Aes256CbcPkcs7;

            // Second, choose an authentication (message integrity) scheme.
            //
            // In this example we use the master key length to change from HMACSHA256 to
            // HMACSHA384, but that is completely arbitrary. This mostly represents a
            // "cryptographic needs change over time" scenario.
            AeMac aeMac = masterKey.Length < 48 ? AeMac.HMACSHA256 : AeMac.HMACSHA384;

            // It's good to be able to identify what choices were made when a message was
            // encrypted, so that the message can later be decrypted. This allows for
            // future versions to add support for new encryption schemes, but still be
            // able to read old data. A practice known as "cryptographic agility".
            //
            // This is similar in practice to PKCS#7 messaging, but this uses a
            // private-scoped byte rather than a public-scoped Object IDentifier (OID).
            // Please note that the scheme in this example adheres to no particular
            // standard, and is unlikely to survive to a more complete implementation in
            // the .NET Framework.
            //
            // You may be well-served by prepending a version number byte to this
            // message, but may want to avoid the value 0x30 (the leading byte value for
            // DER-encoded structures such as X.509 certificates and PKCS#7 messages).
            byte[] algorithmChoices = { (byte)aeCipher, (byte)aeMac };
            byte[] iv;
            byte[] cipherText;
            byte[] tag;

            // Using our algorithm choices, open an HMAC (as an authentication tag
            // generator) and a SymmetricAlgorithm which use different keys each derived
            // from the same master key.
            //
            // A custom implementation may very well have distinctly managed secret keys
            // for the MAC and cipher, this example merely demonstrates the master to
            // derived key methodology to encourage key separation from the MAC and
            // cipher keys.
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
                using (ICryptoTransform encryptor = cipher.CreateEncryptor())
                {
                    // Since no IV was provided, a random one has been generated
                    // during the call to CreateEncryptor.
                    //
                    // But note that it only does the auto-generation once. If the cipher
                    // object were used again, a call to GenerateIV would have been
                    // required.
                    iv = cipher.IV;

                    cipherText = Transform(encryptor, message, 0, message.Length);
                }

                // The IV and ciphertest both need to be included in the MAC to prevent
                // tampering.
                //
                // By including the algorithm identifiers, we have technically moved from
                // simple Authenticated Encryption (AE) to Authenticated Encryption with
                // Additional Data (AEAD). By including the algorithm identifiers in the
                // MAC, it becomes harder for an attacker to change them as an attempt to
                // perform a downgrade attack.
                //
                // If you've added a data format version field, it can also be included
                // in the MAC to further inhibit an attacker's options for confusing the
                // data processor into believing the tampered message is valid.
                tagGenerator.AppendData(algorithmChoices);
                tagGenerator.AppendData(iv);
                tagGenerator.AppendData(cipherText);
                tag = tagGenerator.GetHashAndReset();
            }

            // Build the final result as the concatenation of everything except the keys.
            int totalLength =
                algorithmChoices.Length +
                tag.Length +
                iv.Length +
                cipherText.Length;

            byte[] output = new byte[totalLength];
            int outputOffset = 0;

            Append(algorithmChoices, output, ref outputOffset);
            Append(tag, output, ref outputOffset);
            Append(iv, output, ref outputOffset);
            Append(cipherText, output, ref outputOffset);

            Debug.Assert(outputOffset == output.Length);
            return output;
        }

        /// <summary>
        /// Reads a message produced by <see cref="Encrypt"/> after verifying it hasn't
        /// been tampered with.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="cipherText">
        /// The output of <see cref="Encrypt"/>: a concatenation of a cipher ID, mac ID,
        /// authTag, IV, and cipherText.
        /// </param>
        /// <returns>The decrypted content.</returns>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="masterKey"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="cipherText"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="CryptographicException">
        /// <paramref name="cipherText"/> identifies unknown algorithms, is not long
        /// enough, fails a data integrity check, or fails to decrypt.
        /// </exception>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or larger) value
        /// generated by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>. This implementation chooses to
        /// block deficient inputs by length, but doesn't make any attempt at
        /// discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase),
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Decrypt(byte[] masterKey, byte[] cipherText)
        {
            // This example continues the .NET practice of throwing exceptions for
            // failures. If you consider message tampering to be normal (and thus
            // "not exceptional") behavior, you may like the signature
            // bool Decrypt(byte[] messageKey, byte[] cipherText, out byte[] message)
            // better.
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (cipherText == null)
                throw new ArgumentNullException(nameof(cipherText));

            // The format of this message is assumed to be public, so there's no harm in
            // saying ahead of time that the message makes no sense.
            if (cipherText.Length < 2)
            {
                throw new CryptographicException();
            }

            // Use the message algorithm headers to determine what cipher algorithm and
            // MAC algorithm are going to be used. Since the same Key Derivation
            // Functions (KDFs) are being used in Decrypt as Encrypt, the keys are also
            // the same.
            AeCipher aeCipher = (AeCipher)cipherText[0];
            AeMac aeMac = (AeMac)cipherText[1];

            using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                int blockSizeInBytes = cipher.BlockSize / 8;
                int tagSizeInBytes = tagGenerator.HashSize / 8;
                int headerSizeInBytes = 2;
                int tagOffset = headerSizeInBytes;
                int ivOffset = tagOffset + tagSizeInBytes;
                int cipherTextOffset = ivOffset + blockSizeInBytes;
                int cipherTextLength = cipherText.Length - cipherTextOffset;
                int minLen = cipherTextOffset + blockSizeInBytes;

                // Again, the minimum length is still assumed to be public knowledge,
                // nothing has leaked out yet. The minimum length couldn't just be calculated
                // without reading the header.
                if (cipherText.Length < minLen)
                {
                    throw new CryptographicException();
                }

                // It's very important that the MAC be calculated and verified before
                // proceeding to decrypt the ciphertext, as this prevents any sort of
                // information leaking out to an attacker.
                //
                // Don't include the tag in the calculation, though.

                // First, everything before the tag (the cipher and MAC algorithm ids)
                tagGenerator.AppendData(cipherText, 0, tagOffset);

                // Skip the data before the tag and the tag, then read everything that
                // remains.
                tagGenerator.AppendData(
                    cipherText,
                    tagOffset + tagSizeInBytes,
                    cipherText.Length - tagSizeInBytes - tagOffset);

                byte[] generatedTag = tagGenerator.GetHashAndReset();

                // The time it took to get to this point has so far been a function only
                // of the length of the data, or of non-encrypted values (e.g. it could
                // take longer to prepare the *key* for the HMACSHA384 MAC than the
                // HMACSHA256 MAC, but the algorithm choice wasn't a secret).
                //
                // If the verification of the authentication tag aborts as soon as a
                // difference is found in the byte arrays then your program may be
                // acting as a timing oracle which helps an attacker to brute-force the
                // right answer for the MAC. So, it's very important that every possible
                // "no" (2^256-1 of them for HMACSHA256) be evaluated in as close to the
                // same amount of time as possible. For this, we call CryptographicEquals
                if (!CryptographicEquals(
                    generatedTag,
                    0,
                    cipherText,
                    tagOffset,
                    tagSizeInBytes))
                {
                    // Assuming every tampered message (of the same length) took the same
                    // amount of time to process, we can now safely say
                    // "this data makes no sense" without giving anything away.
                    throw new CryptographicException();
                }

                // Restore the IV into the symmetricAlgorithm instance.
                byte[] iv = new byte[blockSizeInBytes];
                Buffer.BlockCopy(cipherText, ivOffset, iv, 0, iv.Length);
                cipher.IV = iv;

                using (ICryptoTransform decryptor = cipher.CreateDecryptor())
                {
                    return Transform(
                        decryptor,
                        cipherText,
                        cipherTextOffset,
                        cipherTextLength);
                }
            }
        }

        private static byte[] Transform(
            ICryptoTransform transform,
            byte[] input,
            int inputOffset,
            int inputLength)
        {
            // Many of the implementations of ICryptoTransform report true for
            // CanTransformMultipleBlocks, and when the entire message is available in
            // one shot this saves on the allocation of the CryptoStream and the
            // intermediate structures it needs to properly chunk the message into blocks
            // (since the underlying stream won't always return the number of bytes
            // needed).
            if (transform.CanTransformMultipleBlocks)
            {
                return transform.TransformFinalBlock(input, inputOffset, inputLength);
            }

            // If our transform couldn't do multiple blocks at once, let CryptoStream
            // handle the chunking.
            using (MemoryStream messageStream = new MemoryStream())
            using (CryptoStream cryptoStream =
                new CryptoStream(messageStream, transform, CryptoStreamMode.Write))
            {
                cryptoStream.Write(input, inputOffset, inputLength);
                cryptoStream.FlushFinalBlock();
                return messageStream.ToArray();
            }
        }

        /// <summary>
        /// Open a properly configured <see cref="SymmetricAlgorithm"/> conforming to the
        /// scheme identified by <paramref name="aeCipher"/>.
        /// </summary>
        /// <param name="aeCipher">The cipher mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// A SymmetricAlgorithm object with the right key, cipher mode, and padding
        /// mode; or <c>null</c> on unknown algorithms.
        /// </returns>
        private static SymmetricAlgorithm GetCipher(AeCipher aeCipher, byte[] masterKey)
        {
            SymmetricAlgorithm symmetricAlgorithm;

            switch (aeCipher)
            {
                case AeCipher.Aes256CbcPkcs7:
                    symmetricAlgorithm = Aes.Create();
                    // While 256-bit, CBC, and PKCS7 are all the default values for these
                    // properties, being explicit helps comprehension more than it hurts
                    // performance.
                    symmetricAlgorithm.KeySize = 256;
                    symmetricAlgorithm.Mode = CipherMode.CBC;
                    symmetricAlgorithm.Padding = PaddingMode.PKCS7;
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            //
            // Since none of the symmetric encryption algorithms currently in .NET
            // support key sizes greater than 256-bit, we can use HMACSHA256 with
            // NIST SP 800-108 5.1 (Counter Mode KDF) to derive a value that is
            // no smaller than the key size, then Array.Resize to trim it down as
            // needed.

            using (HMAC hmac = new HMACSHA256(masterKey))
            {
                // i=1, Label=ASCII(cipher)
                byte[] cipherKey = hmac.ComputeHash(
                    new byte[] { 1, 99, 105, 112, 104, 101, 114 });

                // Resize the array to the desired keysize. KeySize is in bits,
                // and Array.Resize wants the length in bytes.
                Array.Resize(ref cipherKey, symmetricAlgorithm.KeySize / 8);

                symmetricAlgorithm.Key = cipherKey;
            }

            return symmetricAlgorithm;
        }

        /// <summary>
        /// Open a properly configured <see cref="HMAC"/> conforming to the scheme
        /// identified by <paramref name="aeMac"/>.
        /// </summary>
        /// <param name="aeMac">The message authentication mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// An HMAC object with the proper key, or <c>null</c> on unknown algorithms.
        /// </returns>
        private static HMAC GetMac(AeMac aeMac, byte[] masterKey)
        {
            HMAC hmac;

            switch (aeMac)
            {
                case AeMac.HMACSHA256:
                    hmac = new HMACSHA256();
                    break;
                case AeMac.HMACSHA384:
                    hmac = new HMACSHA384();
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            // Since the output size of the HMAC is the same as the ideal key size for
            // the HMAC, we can use the master key over a fixed input once to perform
            // NIST SP 800-108 5.1 (Counter Mode KDF):
            hmac.Key = masterKey;

            // i=1, Context=ASCII(MAC)
            byte[] newKey = hmac.ComputeHash(new byte[] { 1, 77, 65, 67 });

            hmac.Key = newKey;
            return hmac;
        }

        // A simple helper method to ensure that the offset (writePos) always moves
        // forward with new data.
        private static void Append(byte[] newData, byte[] combinedData, ref int writePos)
        {
            Buffer.BlockCopy(newData, 0, combinedData, writePos, newData.Length);
            writePos += newData.Length;
        }

        /// <summary>
        /// Compare the contents of two arrays in an amount of time which is only
        /// dependent on <paramref name="length"/>.
        /// </summary>
        /// <param name="a">An array to compare to <paramref name="b"/>.</param>
        /// <param name="aOffset">
        /// The starting position within <paramref name="a"/> for comparison.
        /// </param>
        /// <param name="b">An array to compare to <paramref name="a"/>.</param>
        /// <param name="bOffset">
        /// The starting position within <paramref name="b"/> for comparison.
        /// </param>
        /// <param name="length">
        /// The number of bytes to compare between <paramref name="a"/> and
        /// <paramref name="b"/>.</param>
        /// <returns>
        /// <c>true</c> if both <paramref name="a"/> and <paramref name="b"/> have
        /// sufficient length for the comparison and all of the applicable values are the
        /// same in both arrays; <c>false</c> otherwise.
        /// </returns>
        /// <remarks>
        /// An "insufficient data" <c>false</c> response can happen early, but otherwise
        /// a <c>true</c> or <c>false</c> response take the same amount of time.
        /// </remarks>
        [MethodImpl(MethodImplOptions.NoInlining | MethodImplOptions.NoOptimization)]
        private static bool CryptographicEquals(
            byte[] a,
            int aOffset,
            byte[] b,
            int bOffset,
            int length)
        {
            Debug.Assert(a != null);
            Debug.Assert(b != null);
            Debug.Assert(length >= 0);

            int result = 0;

            if (a.Length - aOffset < length || b.Length - bOffset < length)
            {
                return false;
            }

            unchecked
            {
                for (int i = 0; i < length; i++)
                {
                    // Bitwise-OR of subtraction has been found to have the most
                    // stable execution time.
                    //
                    // This cannot overflow because bytes are 1 byte in length, and
                    // result is 4 bytes.
                    // The OR propagates all set bytes, so the differences are only
                    // present in the lowest byte.
                    result = result | (a[i + aOffset] - b[i + bOffset]);
                }
            }

            return result == 0;
        }
    }
}
```

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
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="34847-103">타이밍 ֳ 패딩을 사용 하 여 CBC 모드 대칭 암호 해독</span><span class="sxs-lookup"><span data-stu-id="34847-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="34847-104">현재 알려진된 암호화 연구에 따라 Microsoft 있다고 인식 하는 매우 특정 한 상황을 제외 하 고는 더 이상 확인할 수 있는 안쪽 여백 되었을 때 대칭 암호화의 암호 블록 체인 (CBC) 모드를 사용 하 여 암호화 된 데이터를 해독 하는 안전 암호 텍스트의 무결성을 확인 하지 않고 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-104">Microsoft, based on currently known cryptographic research, believes that, except for very specific circumstances, it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext.</span></span>

## <a name="introduction"></a><span data-ttu-id="34847-105">소개</span><span class="sxs-lookup"><span data-stu-id="34847-105">Introduction</span></span>

<span data-ttu-id="34847-106">패딩 oracle 공격에 키를 알 필요 없이 데이터의 내용을 해독 하도록 허용 하는 암호화 된 데이터에 대 한 공격의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-106">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="34847-107">Oracle에는 "알릴"을 실행 하는 작업 올바른 인지 여부에 대 한 공격자가 정보가 제공 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-107">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="34847-108">스 보드 재생 다음과 같이 가정해 봅니다 또는 자식이 있는 게임 카드입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-108">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="34847-109">때 그녀의 얼굴 켜지는 큰 웃는 얼굴와 그녀는 그녀가 생각 하기 때문에 이동 하려면 빈 좋은 oracle를 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-109">When her face lights up with a big smile because she thinks she's about to make a good move, that's an oracle.</span></span> <span data-ttu-id="34847-110">는 상대도 사용할 수 있습니다이 oracle 다음 이사를 적절 하 게 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-110">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="34847-111">안쪽 여백은 특정 암호화 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-111">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="34847-112">일부 암호화는 데이터를 암호화 하는 데 사용 되는 알고리즘은 각 블록의 크기가 고정된 되어 있는 데이터 블록에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-112">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="34847-113">데이터를 암호화 하려는 올바른 크기는 블록에 맞게 없다면 완료 될 때까지 데이터 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="34847-113">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="34847-114">다양 한 형식의 안쪽 여백에는 항상 있어야 하는 원래 입력 올바른 크기의 경우에 해당 패딩이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-114">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="34847-115">따라서 항상 안전 하 게 제거할 암호 해독 시 안쪽 여백 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-115">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="34847-116">다음 두 가지를 함께 배치 패딩 oracle 소프트웨어 구현을 암호 해독 된 데이터에 유효한 안쪽 여백에 있는지 여부를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-116">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="34847-117">Oracle 같은 간단한 "잘못 된 패딩" 라고 표시 하는 값을 반환 하거나 조금 더 복잡 한 눈에 띄게 다른 시간 잘못 된 블록이 아닌 유효한 블록을 처리 하는 것과 같은 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-117">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="34847-118">암호 블록 기반 다른 이라는 속성을, 두 번째 블록에 있는 데이터의 첫 번째 블록에 데이터의 관계를 결정 하는 모드 등에입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-118">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="34847-119">CBC는 가장 자주 사용 되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-119">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="34847-120">CBC로는 IV (Initialization Vector), 알려진 초기 임의 블록을 정의 하 고 동일한 키가 있는 동일한 메시지를 암호화 하지 않습니다 항상 생성 되는 동일한 암호화 된 출력 하기 위해 정적 암호화의 결과 함께 이전 블록을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-120">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="34847-121">공격자가 CBC 데이터가 구조화 되는 방식을 함께에서 패딩 oracle, צ ְ ײ, oracle를 노출 하는 코드를 약간 변경 된 메시지를 보내고 oracle ¿ë à ú 될 때까지 데이터를 보내는 유지 데이터가 올바른지 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-121">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="34847-122">이 응답에서 공격자는 바이트 단위로 메시지를 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-122">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="34847-123">최신 컴퓨터 네트워크는 이러한 높은 품질 공격자 매우 작은 (0.1 밀리초 미만) 원격 시스템에서 실행의 차이점에에서 시간을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-123">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span> <span data-ttu-id="34847-124">데이터가 변조 되지 않은 경우 성공적으로 암호 해독만 발생할 수 있음을 가정 하는 응용 프로그램 성공 하거나 실패 한 암호 해독의 차이 관찰 하도록 설계 된 도구에서 공격에 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-124">Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="34847-125">이러한 시간 차이로 다른 항목 보다 일부 언어 또는 라이브러리에서 더 큰 수 있지만, 이제 믿고는 모든 언어 및 라이브러리에 대 한 유용한 위협 경우에 응용 프로그램의 오류에 대응 고려 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34847-125">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="34847-126">이 공격 암호화 된 데이터를 변경 하 고는 oracle 결과 테스트할 수 있는 기능에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-126">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="34847-127">완전히 방지할 수 있었던 공격을 완화 하는 유일한 방법은 암호화 된 데이터의 변경 내용을 감지 하 여 모든 작업을 실행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-127">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="34847-128">이 작업을 수행 하는 표준 방법은 데이터에 대 한 서명을 만드는 모든 작업을 수행 하기 전에 해당 서명 유효성 검사를 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-128">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="34847-129">서명이 확인할 수 있어야 합니다., 공격자가 만들 수 없습니다, 그리고 그렇지 않으면 암호화 된 데이터를 변경할 것 다음 변경 된 데이터를 기반으로 새 서명을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-129">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="34847-130">한 가지 일반적인 유형의 적절 한 서명이 키 지정 해시 메시지 인증 코드 (HMAC) 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-130">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="34847-131">HMAC 걸리는 비밀 키 HMAC를 생성 하는 사람에만 하 고 유효성을 검사 하는 사람에 알려진 점에서 체크섬과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="34847-131">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="34847-132">키를 소유한 없이 올바른 HMAC를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-132">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="34847-133">데이터를 받으면 암호화 된 데이터를 독립적으로 계산 하지 비밀 키를 사용 하 여 HMAC 하는 보낸 사람에 게 공유 힙이고 있습니다를 보낸 것에 대해 HMAC를 계산 하는 비교 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-133">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="34847-134">이 비교 상수 시간 이어야 합니다., 그렇지 않으면 사용자가 추가한 다른 감지 oracle 다른 종류의 공격을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-134">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="34847-135">요약 하자면, 사용 하는 CBC 블록 암호화를 안전 하 게 패딩, HMAC (또는 다른 데이터 무결성 검사) 시도 하기 전에 분할 된 시간 비교를 사용 하 여 데이터를 암호 해독의 유효성을 검사 하는 결합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-135">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="34847-136">이후 변경 된 모든 메시지에 응답을 생성 하기 위해 동일한 양 시간이 걸릴 수 있었던 공격 금지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34847-136">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="34847-137">취약 한 누구 입니까</span><span class="sxs-lookup"><span data-stu-id="34847-137">Who is vulnerable</span></span>

<span data-ttu-id="34847-138">이 취약성 자체 암호화 및 암호 해독을 수행 하 고 있는 관리 및 네이티브 응용 프로그램에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34847-138">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="34847-139">이 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="34847-139">This includes, for example:</span></span>

- <span data-ttu-id="34847-140">서버에서 이상 암호 해독에 대 한 쿠키를 암호화 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-140">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="34847-141">열이 있는 테이블에 데이터를 삽입 하는 사용자에 대 한 기능을 제공 하는 데이터베이스 응용 프로그램을 나중에 암호 해독 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34847-141">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="34847-142">데이터 전송 중에 데이터를 보호 하는 공유 키를 사용 하 여 암호화를 사용 하는 응용 프로그램을 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-142">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="34847-143">암호화 하 고 "내부" TLS 터널 메시지를 해독 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-143">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="34847-144">단독 TLS를 사용 하 여 수 보호할 수 없으며 이러한 시나리오에서 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-144">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="34847-145">취약 한 응용 프로그램:</span><span class="sxs-lookup"><span data-stu-id="34847-145">A vulnerable application:</span></span>

- <span data-ttu-id="34847-146">CBC 암호화 모드를 사용 하 여 PKCS #7 또는 ANSI X.923 같은 확인할 수 있는 안쪽 여백 모드에서 데이터를 해독 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-146">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="34847-147">MAC 또는 비대칭는 디지털 서명) (통해 데이터 무결성 검사를 수행할 필요 없이 암호 해독을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-147">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="34847-148">암호화 메시지 구문 (PKCS #7/CMS) EnvelopedData 구조와 같은 이러한 기본 형식 맨 위에 추상화를 기반으로 빌드된 응용 프로그램에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34847-148">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="34847-149">관련된 문제 영역을</span><span class="sxs-lookup"><span data-stu-id="34847-149">Related areas of concern</span></span>

<span data-ttu-id="34847-150">Research는 ISO 10126에 해당 하는 메시지에는 잘 알려진 또는 예측 가능한 바닥글 구조 때 패딩 채워져 CBC 메시지에 대 한 추가 문제는 그리 Microsoft 졌 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-150">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="34847-151">W3C XML 암호화 구문 및 처리 권장 사항 (xmlenc EncryptedXml)의 규칙을 따를 준비 된 콘텐츠 예를 들어입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-151">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="34847-152">W3C 지침을 암호화 한 다음 메시지에 서명 된 시간에 적절 한 고려 되었지만, 이제 좋습니다 항상 암호화 then-기호 (+)를 수행 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-152">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="34847-153">비대칭 키와 임의의 메시지 간의 내재 된 트러스트 관계가 없는 없기 때문에 항상 응용 프로그램 개발자는 비대칭 서명 키의 적용 여부를 확인 하는 중에 주의 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-153">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="34847-154">설명</span><span class="sxs-lookup"><span data-stu-id="34847-154">Details</span></span>

<span data-ttu-id="34847-155">지금까지 암호화 및 중요 한 데이터를 HMAC 또는 RSA 서명 등의 방법을 사용 하 여 인증 해야 합의 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-155">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="34847-156">그러나 암호화 및 인증 작업을 시퀀싱 하는 방법에 대 한 명확한 지침 덜 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-156">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="34847-157">이 문서에 자세히 설명 하는 취약점으로 인해 Microsoft의 지침이 되었습니다 항상 "암호화 then-기호" 패러다임을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-157">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="34847-158">즉, 먼저 대칭 키를 사용 하 여 데이터를 암호화 한 다음 암호 텍스트 (암호화 된 데이터)을 통해 MAC 또는 비대칭 서명 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-158">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="34847-159">데이터의 암호를 해독 하는 경우에 반대로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-159">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="34847-160">먼저, MAC 또는 암호화, 서명 확인 다음 암호를 해독 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-160">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="34847-161">"Oracle 공격 패딩" 것으로 알려져 10 년에 대 한 알려진 취약점의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-161">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="34847-162">이러한 취약점 4096 개 이하의 시도/데이터 블록을 사용 하 여 AES 및 3DES, 같은 대칭 블록 알고리즘으로 암호화 된 데이터를 해독 하는 공격자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-162">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="34847-163">이러한 취약점 확인 사용 하 여 암호를 차단 하는 팩트의 끝에 패딩 확인할 수 있는 데이터와 함께 가장 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34847-163">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="34847-164">공격자가 암호화 텍스트를 변조할 수 있고 확인 여부는 변조 끝에 패딩의 형식에 오류가 발생, 있는 경우 공격자가 데이터를 해독할 수를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-164">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="34847-165">서비스에서 반환 되는 패딩 ASP.NET 취약점 같은 유효 했는지 여부에 따라 서로 다른 오류 코드에 기반한 실용적인 공격 처음에 [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-165">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](https://technet.microsoft.com/library/security/ms10-070.aspx).</span></span> <span data-ttu-id="34847-166">그러나 Microsoft 타이밍 처리 유효 하지 않은 패딩의에서 차이 만큼만 사용 하 여 비슷한 공격을 수행할 실용적이 이제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-166">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="34847-167">정보를 표시 하지 않고 데이터 무결성을 확인할 수는 서명을 사용 하는 암호화 체계 권한과 (관계 없이 내용)는 데이터의 지정 된 길이 대 한 고정 런타임과 서명 확인이 수행 하는 통해 공격자는 [쪽 채널](https://en.wikipedia.org/wiki/Side-channel_attack)합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-167">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="34847-168">무결성 검사가 변조 된 모든 메시지를 거부 하는 이후 안쪽 여백 oracle 위협 완화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34847-168">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="34847-169">지침</span><span class="sxs-lookup"><span data-stu-id="34847-169">Guidance</span></span>

<span data-ttu-id="34847-170">무엇 보다도, 모든 데이터 또는 기밀 있는 필요를 통해 보안 TLS (전송 계층), 후속 Secure Sockets Layer (SSL)를 전송 될 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-170">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="34847-171">다음으로 응용 프로그램을 분석:</span><span class="sxs-lookup"><span data-stu-id="34847-171">Next, analyze your application to:</span></span>

- <span data-ttu-id="34847-172">수행 하는 어떤 암호화 정확 하 게 이해 하 고 플랫폼 및 Api를 사용 하는에서 제공 되 고 어떤 암호화 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="34847-172">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="34847-173">확신할 수은 대칭의 각 계층에서 각 사용 [블록 암호화 알고리즘](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)AES 및 3DES CBC 모드에서 비밀 키가 지정 된 데이터 무결성 검사를 사용 하는 통합 등 (프로그램 비대칭 서명은 HMAC 암호화 모드를 변경 하려면 [암호화 인증](https://en.wikipedia.org/wiki/Authenticated_encryption) GCM 등 CCM (AE) 모드).</span><span class="sxs-lookup"><span data-stu-id="34847-173">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="34847-174">현재 조사 결과에 따라, 일반적으로 믿고 비 AE 모드 암호화에 대 한 인증 및 암호화 단계가 독립적으로 수행 됩니다 때 인증 암호 텍스트 (암호화-then-기호) 임을 일반 수 있는 최상의 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-174">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="34847-175">그러나 암호화를 일괄적으로 적용할 올바른 응답이 없습니다 및이 일반화 전문 cryptographer에서 최적의 상태로 방향이 지정 된 도움말 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-175">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="34847-176">인증 되지 않은 CBC 암호 해독을 수행 하지만 해당 메시징 형식을 변경할 수 없는 응용 프로그램이 같은 완화를 통합 하려고 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-176">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="34847-177">확인 하거나 안쪽 여백을 제거 하려면 암호 해독기를 허용 하지 않고 암호 해독:</span><span class="sxs-lookup"><span data-stu-id="34847-177">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="34847-178">적용 된 채움을 여전히 제거 / 무시 해야, 응용 프로그램에 부담을 이동 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-178">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="34847-179">기능은 다른 응용 프로그램 데이터 확인 논리에 안쪽 여백 확인 및 제거를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-179">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="34847-180">일정 한 시간에 안쪽 여백 확인 및 데이터 확인 작업을 수행할 수 있습니다, 위협을 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="34847-180">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="34847-181">안쪽 여백의 해석은 변경 인식된 메시지 길이, 이후 있을 수 있습니다이 방법에서 발생 하는 타이밍 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-181">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="34847-182">I s o 10126를 암호 해독 패딩 모드를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-182">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="34847-183">I s o 10126 암호 해독 패딩은 PKCS7 암호화 패딩입니다 및 ANSIX923 암호화 패딩입니다 모두와 호환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34847-183">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="34847-184">모드를 변경 하면이 안쪽 여백 oracle 기술을 전체 블록 대신 1 바이트를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-184">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="34847-185">그러나 콘텐츠를 닫기 XML 요소 등의 잘 알려진 바닥글 경우 관련된 공격 메시지의 나머지 공격을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-185">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="34847-186">또한이 경우 공격자가 서로 다른 메시지 오프셋으로 여러 번 암호화 될 수 동일한 일반 강제 변환할 수에 일반 텍스트 복구를 하지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-186">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="34847-187">게이트 타이밍 신호를 완화 시킬 암호 해독 호출의 평가:</span><span class="sxs-lookup"><span data-stu-id="34847-187">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="34847-188">보류 시간 계산에 시간 안쪽 여백을 포함 된 모든 데이터 세그먼트 데 소요 되는 암호 해독 작업의 최대 크기를 초과 하는 최소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-188">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="34847-189">제공 된 지침에 따라 시간 계산을 수행 해야 [고해상도 타임 스탬프를 가져오는](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx)를 사용 하 여 <xref:System.Environment.TickCount?displayProperty=nameWithType> (오버플로 롤 over /)에 따라 나 빼기 (NTP 조정에 따라 두 개의 시스템 타임 스탬프 오류)입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-189">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](https://msdn.microsoft.com/library/windows/desktop/dn55340.aspx), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="34847-190">시간 계산 관리 되어야 합니다. 암호 해독 작업의 모든 잠재적 예외를 포함 하 여 포함 또는 c + + 응용 프로그램 뿐 아니라 끝에 패딩 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-190">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="34847-191">성공 또는 실패 확인 된 경우에 아직, 타이밍 게이트를 만료 될 때 오류를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-191">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="34847-192">인증 되지 않은 암호 해독을 수행 하는 서비스 모니터링을 통해 "잘못 된" 메시지의 양이 했음을 감지 하는 기능이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-192">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="34847-193">이 신호 (합법적으로 손상 된 데이터) 거짓 긍정 및 거짓 부 정의 (공격을 탐지를 피하도록 충분히 긴 시간 동안 분배)를 전달 하는 것을 염두에 두십시오.</span><span class="sxs-lookup"><span data-stu-id="34847-193">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="34847-194">취약 한 코드-네이티브 응용 프로그램 찾기</span><span class="sxs-lookup"><span data-stu-id="34847-194">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="34847-195">Windows 암호화에 대해 작성 하는 프로그램에 대 한: 차세대 (CNG) 라이브러리:</span><span class="sxs-lookup"><span data-stu-id="34847-195">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="34847-196">암호 해독 호출이 [BCryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa375391.aspx)을 지정 하는 `BCRYPT_BLOCK_PADDING` 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-196">The decryption call is to [BCryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa375391.aspx), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="34847-197">키 핸들 호출 하 여 활성화 되었습니다 [BCryptSetProperty](https://msdn.microsoft.com/library/windows/desktop/aa375504.aspx) 와 [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) 로 설정 `BCRYPT_CHAIN_MODE_CBC`합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-197">The key handle has been initialized by calling [BCryptSetProperty](https://msdn.microsoft.com/library/windows/desktop/aa375504.aspx) with [BCRYPT_CHAINING_MODE](https://msdn.microsoft.com/library/windows/desktop/aa376211.aspx#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="34847-198">이후 `BCRYPT_CHAIN_MODE_CBC` 은 기본값인 영향을 받는 코드에 대 한 모든 값 할당 되지 않을 수 있습니다 `BCRYPT_CHAINING_MODE`합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-198">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="34847-199">이전 Windows 암호화 API에 대해 빌드된 프로그램:</span><span class="sxs-lookup"><span data-stu-id="34847-199">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="34847-200">암호 해독 호출이 [CryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa379913.aspx) 와 `Final=TRUE`합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-200">The decryption call is to [CryptDecrypt](https://msdn.microsoft.com/library/windows/desktop/aa379913.aspx) with `Final=TRUE`.</span></span>
- <span data-ttu-id="34847-201">키 핸들 호출 하 여 활성화 되었습니다 [CryptSetKeyParam](https://msdn.microsoft.com/library/windows/desktop/aa380272.aspx) 와 [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) 로 설정 `CRYPT_MODE_CBC`합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-201">The key handle has been initialized by calling [CryptSetKeyParam](https://msdn.microsoft.com/library/windows/desktop/aa380272.aspx) with [KP_MODE](https://msdn.microsoft.com/library/windows/desktop/aa379949.aspx#KP_MODE) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="34847-202">이후 `CRYPT_MODE_CBC` 은 기본값인 영향을 받는 코드에 대 한 모든 값 할당 되지 않을 수 있습니다 `KP_MODE`합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-202">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="34847-203">취약 한 코드 찾기-관리 되는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="34847-203">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="34847-204">암호 해독 호출 하는 것은 <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> 또는 <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> 에 대 한 메서드 <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-204">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="34847-205">이.NET 내에서 다음 파생된 형식을 포함 되지만 타사 형식을 포함 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-205">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
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
- <span data-ttu-id="34847-206"><xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> 속성이로 설정 된 <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, 또는 <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-206">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="34847-207">이후 <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> 은 기본값인 영향을 받는 코드 되지 할당 했는 <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-207">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="34847-208"><xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> 속성이로 설정 된 <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="34847-208">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="34847-209">이후 <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> 은 기본값인 영향을 받는 코드 되지 할당 했는 <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-209">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="34847-210">암호화 메시지 구문 취약 한 코드-찾기</span><span class="sxs-lookup"><span data-stu-id="34847-210">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="34847-211">암호화 된 내용이 AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), (1.3.14.3.2.7) DES, 3DES CBC 모드를 사용 하는 인증 되지 않은 CMS EnvelopedData 메시지 (1.2.840.113549.3.7) 또는 RC2 (1.2.840.113549.3.2)은 취약 한도 메시지 블록의 암호화 알고리즘을 사용 하 여 CBC 모드에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-211">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="34847-212">스트림 암호화가 문제에 취약 하지 않으면 동안 항상 ContentEncryptionAlgorithm 값 검사를 통해 데이터를 인증 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-212">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="34847-213">관리 되는 응용 프로그램에 대 한 blob 수 CMS EnvelopedData에 전달 되는 모든 값을 검색 <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-213">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="34847-214">네이티브 응용 프로그램에 대 한 CMS EnvelopedData blob를 검색할 수 있는 CMS 핸들을 통해에 지정 된 값으로 [CryptMsgUpdate](https://msdn.microsoft.com/library/windows/desktop/aa380231.aspx) 인 결과 [CMSG_TYPE_PARAM](https://msdn.microsoft.com/library/windows/desktop/aa380227.aspx) 은 `CMSG_ENVELOPED` CMS 핸들은 및/또는 나중에 보낸는 `CMSG_CTRL_DECRYPT` 명령을 통해 [CryptMsgControl](https://msdn.microsoft.com/library/windows/desktop/aa380220.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-214">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](https://msdn.microsoft.com/library/windows/desktop/aa380231.aspx) whose resulting [CMSG_TYPE_PARAM](https://msdn.microsoft.com/library/windows/desktop/aa380227.aspx) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](https://msdn.microsoft.com/library/windows/desktop/aa380220.aspx).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="34847-215">취약 한 코드 예제에서는-관리</span><span class="sxs-lookup"><span data-stu-id="34847-215">Vulnerable code example - managed</span></span>

<span data-ttu-id="34847-216">이 메서드는 쿠키를 읽고 해독과 데이터 무결성 검사 없이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34847-216">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="34847-217">따라서이 방법으로 읽을 수 있는 쿠키의 내용이 받은 사람, 사용자 또는 암호화 된 쿠키 값은 확보 하는 모든 공격자가 공격 받을 수입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-217">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

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

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="34847-218">예제 코드 다음 사례-관리 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-218">Example code following recommended practices - managed</span></span>

<span data-ttu-id="34847-219">다음 샘플 코드의 비표준 메시지 형식을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="34847-219">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="34847-220">여기서는 `cipher_algorithm_id` 및 `hmac_algorithm_id` 알고리즘 식별자는 해당 알고리즘의 로컬 응용 프로그램 (비표준) 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-220">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="34847-221">이러한 식별자 합리적 대신 기존 메시징 프로토콜의 다른 부분에 완전 연결된 bytestream으로입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-221">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="34847-222">또한이 예제에서는 HMAC 키와 암호화 키를 파생 하는 단일 마스터 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-222">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="34847-223">이 기능을 하기 위해 두 키와 다른 값을 유지 하 고 이중 키가 지정 된 응용 프로그램에 단일 키가 지정 된 응용 프로그램에 대 한 편의 위해 둘 다 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34847-223">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="34847-224">HMAC 키와 암호화 키 동기화 되지 않을 수 없습니다 자세한 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-224">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="34847-225">이 샘플을 허용 하지 않습니다는 <xref:System.IO.Stream> 암호화 또는 암호 해독 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-225">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="34847-226">현재 데이터 형식을 사용 하면 단일 패스 암호화 어려운 때문에 `hmac_tag` 값 앞에 오는 암호 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="34847-226">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="34847-227">그러나이 형식은 모든 고정 크기 요소 구문 분석기를 보다 간단 하 게에 유지 되기 때문에 선택 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-227">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="34847-228">이 데이터 형식으로 구현 자가 GetHashAndReset를 호출 하 고 TransformFinalBlock를 호출 하기 전에 결과 확인 하는 주의가 요구는 있지만 단일 패스 decrypt이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="34847-228">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="34847-229">중요 한 스트리밍 암호화의 경우 서로 다른 AE 모드 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34847-229">If streaming encryption is important, then a different AE mode may be required.</span></span>

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

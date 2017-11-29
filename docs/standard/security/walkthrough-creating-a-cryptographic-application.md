---
title: "연습: 암호화 응용 프로그램 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [NET Framework], example
- cryptography [NET Framework], cryptographic application example
- cryptography [NET Framework], application example
ms.assetid: abf48c11-1e72-431d-9562-39cf23e1a8ff
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ab596fd10de81e60e6396268cbd5c5b31aa13078
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-creating-a-cryptographic-application"></a><span data-ttu-id="7cfcb-102">연습: 암호화 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-102">Walkthrough: Creating a Cryptographic Application</span></span>
<span data-ttu-id="7cfcb-103">이 연습에서는 콘텐츠를 암호화 및 암호 해독하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-103">This walkthrough demonstrates how to encrypt and decrypt content.</span></span> <span data-ttu-id="7cfcb-104">코드 예제는 Windows Forms 응용 프로그램용으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-104">The code examples are designed for a Windows Forms application.</span></span> <span data-ttu-id="7cfcb-105">이 응용 프로그램은 스마트 카드 사용과 같은 실제 시나리오를 보여 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-105">This application does not demonstrate real world scenarios, such as using smart cards.</span></span> <span data-ttu-id="7cfcb-106">대신, 암호화 및 암호 해독의 기초를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-106">Instead, it demonstrates the fundamentals of encryption and decryption.</span></span>  
  
 <span data-ttu-id="7cfcb-107">이 연습에서는 암호화에 대한 다음 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-107">This walkthrough uses the following guidelines for encryption:</span></span>  
  
-   <span data-ttu-id="7cfcb-108">대칭 알고리즘인 <xref:System.Security.Cryptography.RijndaelManaged> 클래스를 사용하여 자동으로 생성된 해당 <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> 및 <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>를 통해 데이터를 암호화 및 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-108">Use the <xref:System.Security.Cryptography.RijndaelManaged> class, a symmetric algorithm, to encrypt and decrypt data by using its automatically generated <xref:System.Security.Cryptography.SymmetricAlgorithm.Key%2A> and <xref:System.Security.Cryptography.SymmetricAlgorithm.IV%2A>.</span></span>  
  
-   <span data-ttu-id="7cfcb-109">비대칭 알고리즘인 <xref:System.Security.Cryptography.RSACryptoServiceProvider>를 사용하여 <xref:System.Security.Cryptography.RijndaelManaged>를 통해 암호화된 데이터에 대한 키를 암호화 및 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-109">Use the <xref:System.Security.Cryptography.RSACryptoServiceProvider>, an asymmetric algorithm, to encrypt and decrypt the key to the data encrypted by <xref:System.Security.Cryptography.RijndaelManaged>.</span></span> <span data-ttu-id="7cfcb-110">비대칭 알고리즘은 키와 같은 적은 양의 데이터에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-110">Asymmetric algorithms are best used for smaller amounts of data, such as a key.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7cfcb-111">암호화된 콘텐츠를 다른 사용자와 교환하는 대신 컴퓨터에서 데이터를 보호하려는 경우 <xref:System.Security.Cryptography.ProtectedData> 또는 <xref:System.Security.Cryptography.ProtectedMemory> 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-111">If you want to protect data on your computer instead of exchanging encrypted content with other people, consider using the <xref:System.Security.Cryptography.ProtectedData> or <xref:System.Security.Cryptography.ProtectedMemory> classes.</span></span>  
  
 <span data-ttu-id="7cfcb-112">다음 표에는 이 항목의 암호화 작업이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-112">The following table summarizes the cryptographic tasks in this topic.</span></span>  
  
|<span data-ttu-id="7cfcb-113">작업</span><span class="sxs-lookup"><span data-stu-id="7cfcb-113">Task</span></span>|<span data-ttu-id="7cfcb-114">설명</span><span class="sxs-lookup"><span data-stu-id="7cfcb-114">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="7cfcb-115">Windows Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-115">Creating a Windows Forms application</span></span>|<span data-ttu-id="7cfcb-116">응용 프로그램을 실행하는 데 필요한 컨트롤을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-116">Lists the controls that are required to run the application.</span></span>|  
|<span data-ttu-id="7cfcb-117">전역 개체 선언</span><span class="sxs-lookup"><span data-stu-id="7cfcb-117">Declaring global objects</span></span>|<span data-ttu-id="7cfcb-118"><xref:System.Windows.Forms.Form> 클래스의 전역 컨텍스트를 사용하도록 문자열 경로 변수, <xref:System.Security.Cryptography.CspParameters> 및 <xref:System.Security.Cryptography.RSACryptoServiceProvider>를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-118">Declares string path variables, the <xref:System.Security.Cryptography.CspParameters>, and the <xref:System.Security.Cryptography.RSACryptoServiceProvider> to have global context of the <xref:System.Windows.Forms.Form> class.</span></span>|  
|<span data-ttu-id="7cfcb-119">비대칭 키 만들기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-119">Creating an asymmetric key</span></span>|<span data-ttu-id="7cfcb-120">비대칭 공개 및 개인 키 값 쌍을 만들고 키 컨테이너 이름을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-120">Creates an asymmetric public and private key value pair and assigns it a key container name.</span></span>|  
|<span data-ttu-id="7cfcb-121">파일 암호화</span><span class="sxs-lookup"><span data-stu-id="7cfcb-121">Encrypting a file</span></span>|<span data-ttu-id="7cfcb-122">암호화를 위해 파일을 선택할 수 있는 대화 상자를 표시하고 파일을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-122">Displays a dialog box to select a file for encryption and encrypts the file.</span></span>|  
|<span data-ttu-id="7cfcb-123">파일 암호 해독</span><span class="sxs-lookup"><span data-stu-id="7cfcb-123">Decrypting a file</span></span>|<span data-ttu-id="7cfcb-124">암호 해독을 위해 암호화된 파일을 선택할 수 있는 대화 상자를 표시하고 파일을 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-124">Displays a dialog box to select an encrypted file for decryption and decrypts the file.</span></span>|  
|<span data-ttu-id="7cfcb-125">개인 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-125">Getting a private key</span></span>|<span data-ttu-id="7cfcb-126">키 컨테이너 이름을 사용하여 전체 키 쌍을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-126">Gets the full key pair using the key container name.</span></span>|  
|<span data-ttu-id="7cfcb-127">공개 키 내보내기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-127">Exporting a public key</span></span>|<span data-ttu-id="7cfcb-128">public 매개 변수만 사용하여 키를 XML 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-128">Saves the key to an XML file with only public parameters.</span></span>|  
|<span data-ttu-id="7cfcb-129">공개 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-129">Importing a public key</span></span>|<span data-ttu-id="7cfcb-130">XML 파일의 키를 키 컨테이너에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-130">Loads the key from an XML file into the key container.</span></span>|  
|<span data-ttu-id="7cfcb-131">응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="7cfcb-131">Testing the application</span></span>|<span data-ttu-id="7cfcb-132">이 응용 프로그램을 테스트하기 위한 절차를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-132">Lists procedures for testing this application.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="7cfcb-133">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7cfcb-133">Prerequisites</span></span>  
 <span data-ttu-id="7cfcb-134">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-134">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="7cfcb-135"><xref:System.IO> 및 <xref:System.Security.Cryptography> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="7cfcb-135">References to the <xref:System.IO> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
## <a name="creating-a-windows-forms-application"></a><span data-ttu-id="7cfcb-136">Windows Forms 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-136">Creating a Windows Forms Application</span></span>  
 <span data-ttu-id="7cfcb-137">이 연습의 대다수 코드 예제는 단추 컨트롤에 대한 이벤트 처리기로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-137">Most of the code examples in this walkthrough are designed to be event handlers for button controls.</span></span> <span data-ttu-id="7cfcb-138">다음 표에서는 샘플 응용 프로그램에 필요한 컨트롤 및 코드 예제와 일치하는 데 필요한 이름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-138">The following table lists the controls required for the sample application and their required names to match the code examples.</span></span>  
  
|<span data-ttu-id="7cfcb-139">컨트롤</span><span class="sxs-lookup"><span data-stu-id="7cfcb-139">Control</span></span>|<span data-ttu-id="7cfcb-140">이름</span><span class="sxs-lookup"><span data-stu-id="7cfcb-140">Name</span></span>|<span data-ttu-id="7cfcb-141">텍스트 속성(필요에 따라)</span><span class="sxs-lookup"><span data-stu-id="7cfcb-141">Text property (as needed)</span></span>|  
|-------------|----------|---------------------------------|  
|<xref:System.Windows.Forms.Button>|`buttonEncryptFile`|<span data-ttu-id="7cfcb-142">파일 암호화</span><span class="sxs-lookup"><span data-stu-id="7cfcb-142">Encrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonDecryptFile`|<span data-ttu-id="7cfcb-143">파일 암호 해독</span><span class="sxs-lookup"><span data-stu-id="7cfcb-143">Decrypt File</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonCreateAsmKeys`|<span data-ttu-id="7cfcb-144">키 만들기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-144">Create Keys</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonExportPublicKey`|<span data-ttu-id="7cfcb-145">공개 키 내보내기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-145">Export Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonImportPublicKey`|<span data-ttu-id="7cfcb-146">공개 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-146">Import Public Key</span></span>|  
|<xref:System.Windows.Forms.Button>|`buttonGetPrivateKey`|<span data-ttu-id="7cfcb-147">개인 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-147">Get Private Key</span></span>|  
|<xref:System.Windows.Forms.Label>|`label1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog1`||  
|<xref:System.Windows.Forms.OpenFileDialog>|`openFileDialog2`||  
  
 <span data-ttu-id="7cfcb-148">이벤트 처리기를 만들려면 Visual Studio 디자이너에서 해당 단추를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-148">Double-click the buttons in the  Visual Studio designer to create their event handlers.</span></span>  
  
## <a name="declaring-global-objects"></a><span data-ttu-id="7cfcb-149">전역 개체 선언</span><span class="sxs-lookup"><span data-stu-id="7cfcb-149">Declaring Global Objects</span></span>  
 <span data-ttu-id="7cfcb-150">폼의 생성자에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-150">Add the following code to the Form's constructor.</span></span> <span data-ttu-id="7cfcb-151">사용자 환경 및 기본 설정에 맞게 문자열 변수를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-151">Edit the string variables for your environment and preferences.</span></span>  
  
 [!code-csharp[CryptoWalkThru#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#1)]
 [!code-vb[CryptoWalkThru#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#1)]  
  
## <a name="creating-an-asymmetric-key"></a><span data-ttu-id="7cfcb-152">비대칭 키 만들기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-152">Creating an Asymmetric Key</span></span>  
 <span data-ttu-id="7cfcb-153">이 작업은 <xref:System.Security.Cryptography.RijndaelManaged> 키를 암호화 및 암호 해독하는 비대칭 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-153">This task creates an asymmetric key that encrypts and decrypts the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span> <span data-ttu-id="7cfcb-154">이 키는 콘텐츠를 암호화하는 데 사용되었으며 레이블 컨트롤에 키 컨테이너 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-154">This key was used to encrypt the content and it displays the key container name on the label control.</span></span>  
  
 <span data-ttu-id="7cfcb-155">`Create Keys` 단추(`buttonCreateAsmKeys_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-155">Add the following code as the `Click` event handler for the `Create Keys` button (`buttonCreateAsmKeys_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#2)]
 [!code-vb[CryptoWalkThru#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#2)]  
  
## <a name="encrypting-a-file"></a><span data-ttu-id="7cfcb-156">파일 암호화</span><span class="sxs-lookup"><span data-stu-id="7cfcb-156">Encrypting a File</span></span>  
 <span data-ttu-id="7cfcb-157">이 작업에는 두 가지 방법:에 대 한 이벤트 처리기 메서드는 `Encrypt File` 단추 (`buttonEncryptFile_Click`) 및 `EncryptFile` 메서드.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-157">This task involves two methods: the event handler method for the `Encrypt File` button (`buttonEncryptFile_Click`) and the `EncryptFile` method.</span></span> <span data-ttu-id="7cfcb-158">첫 번째 메서드는 파일을 선택할 수 있는 대화 상자를 표시하고 암호화를 수행하는 두 번째 메서드에 파일 이름을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-158">The first method displays a dialog box for selecting a file and passes the file name to the second method, which performs the encryption.</span></span>  
  
 <span data-ttu-id="7cfcb-159">암호화된 콘텐츠, 키 및 IV가 모두 하나의 <xref:System.IO.FileStream>에 저장되며, 이를 암호화 패키지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-159">The encrypted content, key, and IV are all saved to one <xref:System.IO.FileStream>, which is referred to as the encryption package.</span></span>  
  
 <span data-ttu-id="7cfcb-160">`EncryptFile` 메서드는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-160">The `EncryptFile` method does the following:</span></span>  
  
1.  <span data-ttu-id="7cfcb-161"><xref:System.Security.Cryptography.RijndaelManaged> 대칭 알고리즘을 만들어 콘텐츠를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-161">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to encrypt the content.</span></span>  
  
2.  <span data-ttu-id="7cfcb-162"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 만들어 <xref:System.Security.Cryptography.RijndaelManaged> 키를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-162">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to encrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
3.  <span data-ttu-id="7cfcb-163"><xref:System.Security.Cryptography.CryptoStream> 개체를 사용하여 소스 파일의 <xref:System.IO.FileStream>을 바이트 블록 단위로 암호화된 파일의 대상 <xref:System.IO.FileStream> 개체로 읽고 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-163">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and encrypt the <xref:System.IO.FileStream> of the source file, in blocks of bytes, into a destination <xref:System.IO.FileStream> object for the encrypted file.</span></span>  
  
4.  <span data-ttu-id="7cfcb-164">암호화된 키 및 IV의 길이를 확인하고 해당 길이 값의 바이트 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-164">Determines the lengths of the encrypted key and IV, and creates byte arrays of their length values.</span></span>  
  
5.  <span data-ttu-id="7cfcb-165">암호화된 패키지에 키, IV 및 해당 길이 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-165">Writes the Key, IV, and their length values to the encrypted package.</span></span>  
  
 <span data-ttu-id="7cfcb-166">암호화 패키지는 다음 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-166">The encryption package uses the following format:</span></span>  
  
-   <span data-ttu-id="7cfcb-167">키 길이, 0-3바이트</span><span class="sxs-lookup"><span data-stu-id="7cfcb-167">Key length, bytes 0 - 3</span></span>  
  
-   <span data-ttu-id="7cfcb-168">IV 길이, 4-7바이트</span><span class="sxs-lookup"><span data-stu-id="7cfcb-168">IV length, bytes 4 - 7</span></span>  
  
-   <span data-ttu-id="7cfcb-169">암호화된 키</span><span class="sxs-lookup"><span data-stu-id="7cfcb-169">Encrypted key</span></span>  
  
-   <span data-ttu-id="7cfcb-170">IV</span><span class="sxs-lookup"><span data-stu-id="7cfcb-170">IV</span></span>  
  
-   <span data-ttu-id="7cfcb-171">암호화 텍스트</span><span class="sxs-lookup"><span data-stu-id="7cfcb-171">Cipher text</span></span>  
  
 <span data-ttu-id="7cfcb-172">키 및 IV의 길이를 사용하여 파일을 암호 해독하는 데 사용할 수 있는 암호화 패키지의 모든 부분에 대한 시작 지점 및 길이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-172">You can use the lengths of the key and IV to determine the starting points and lengths of all parts of the encryption package, which can then be used to decrypt the file.</span></span>  
  
 <span data-ttu-id="7cfcb-173">`Encrypt File` 단추(`buttonEncryptFile_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-173">Add the following code as the `Click` event handler for the `Encrypt File` button (`buttonEncryptFile_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#3)]
 [!code-vb[CryptoWalkThru#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#3)]  
  
 <span data-ttu-id="7cfcb-174">다음 `EncryptFile` 메서드를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-174">Add the following `EncryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#5)]
 [!code-vb[CryptoWalkThru#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#5)]  
  
## <a name="decrypting-a-file"></a><span data-ttu-id="7cfcb-175">파일 암호 해독</span><span class="sxs-lookup"><span data-stu-id="7cfcb-175">Decrypting a File</span></span>  
 <span data-ttu-id="7cfcb-176">이 작업에는 `Decrypt File` 단추에 대한 이벤트 처리기 메서드(`buttonEncryptFile_Click`) 및 `DecryptFile` 메서드의 두 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-176">This task involves two methods, the event handler method for the `Decrypt File` button (`buttonEncryptFile_Click`), and the `DecryptFile` method.</span></span> <span data-ttu-id="7cfcb-177">첫 번째 메서드는 파일을 선택할 수 있는 대화 상자를 표시하고 암호 해독을 수행하는 두 번째 메서드에 파일 이름을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-177">The first method displays a dialog box for selecting a file and passes its file name to the second method, which performs the decryption.</span></span>  
  
 <span data-ttu-id="7cfcb-178">`Decrypt` 메서드는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-178">The `Decrypt` method does the following:</span></span>  
  
1.  <span data-ttu-id="7cfcb-179"><xref:System.Security.Cryptography.RijndaelManaged> 대칭 알고리즘을 만들어 콘텐츠를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-179">Creates a <xref:System.Security.Cryptography.RijndaelManaged> symmetric algorithm to decrypt the content.</span></span>  
  
2.  <span data-ttu-id="7cfcb-180">암호화된 패키지 <xref:System.IO.FileStream>의 처음 8바이트를 바이트 배열로 읽어 암호화된 키 및 IV의 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-180">Reads the first eight bytes of the <xref:System.IO.FileStream> of the encrypted package into byte arrays to obtain the lengths of the encrypted key and the IV.</span></span>  
  
3.  <span data-ttu-id="7cfcb-181">암호화 패키지에서 바이트 배열로 키 및 IV를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-181">Extracts the key and IV from the encryption package into byte arrays.</span></span>  
  
4.  <span data-ttu-id="7cfcb-182"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 만들어 <xref:System.Security.Cryptography.RijndaelManaged> 키를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-182">Creates an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to decrypt the <xref:System.Security.Cryptography.RijndaelManaged> key.</span></span>  
  
5.  <span data-ttu-id="7cfcb-183"><xref:System.Security.Cryptography.CryptoStream> 개체를 사용하여 <xref:System.IO.FileStream> 암호화 패키지의 암호화 텍스트 섹션을 바이트 블록 단위로 암호 해독된 파일의 <xref:System.IO.FileStream> 개체로 읽고 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-183">Uses a <xref:System.Security.Cryptography.CryptoStream> object to read and decrypt the cipher text section of the <xref:System.IO.FileStream> encryption package, in blocks of bytes, into the <xref:System.IO.FileStream> object for the decrypted file.</span></span> <span data-ttu-id="7cfcb-184">이 작업을 완료하면 암호 해독이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-184">When this is finished, the decryption is completed.</span></span>  
  
 <span data-ttu-id="7cfcb-185">`Decrypt File` 단추에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-185">Add the following code as the `Click` event handler for the `Decrypt File` button.</span></span>  
  
 [!code-csharp[CryptoWalkThru#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#4)]
 [!code-vb[CryptoWalkThru#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#4)]  
  
 <span data-ttu-id="7cfcb-186">다음 `DecryptFile` 메서드를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-186">Add the following `DecryptFile` method to the form.</span></span>  
  
 [!code-csharp[CryptoWalkThru#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#6)]
 [!code-vb[CryptoWalkThru#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#6)]  
  
## <a name="exporting-a-public-key"></a><span data-ttu-id="7cfcb-187">공개 키 내보내기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-187">Exporting a Public Key</span></span>  
 <span data-ttu-id="7cfcb-188">이 작업은 `Create Keys` 단추를 사용하여 만든 키를 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-188">This task saves the key created by the `Create Keys` button to a file.</span></span> <span data-ttu-id="7cfcb-189">public 매개 변수만 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-189">It exports only the public parameters.</span></span>  
  
 <span data-ttu-id="7cfcb-190">이 작업은 Bob이 파일을 암호화할 수 있도록 Alice가 Bob에게 공개 키를 제공하는 시나리오를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-190">This task simulates the scenario of Alice giving Bob her public key so that he can encrypt files for her.</span></span> <span data-ttu-id="7cfcb-191">Bob과 해당 공개 키를 가진 다른 사용자는 private 매개 변수가 있는 전체 키 쌍이 없기 때문에 파일을 암호 해독할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-191">He and others who have that public key will not be able to decrypt them because they do not have the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="7cfcb-192">`Export Public Key` 단추(`buttonExportPublicKey_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-192">Add the following code as the `Click` event handler for the `Export Public Key` button (`buttonExportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#8)]
 [!code-vb[CryptoWalkThru#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#8)]  
  
## <a name="importing-a-public-key"></a><span data-ttu-id="7cfcb-193">공개 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-193">Importing a Public Key</span></span>  
 <span data-ttu-id="7cfcb-194">이 작업은 `Export Public Key` 단추를 사용하여 만든 public 매개 변수만 있는 키를 로드하고 키 컨테이너 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-194">This task loads the key with only public parameters, as created by the `Export Public Key` button, and sets it as the key container name.</span></span>  
  
 <span data-ttu-id="7cfcb-195">이 작업은 Bob이 파일을 암호화할 수 있도록 public 매개 변수만 있는 Alice의 키를 Bob이 로드하는 시나리오를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-195">This task simulates the scenario of Bob loading Alice's key with only public parameters so he can encrypt files for her.</span></span>  
  
 <span data-ttu-id="7cfcb-196">`Import Public Key` 단추(`buttonImportPublicKey_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-196">Add the following code as the `Click` event handler for the `Import Public Key` button (`buttonImportPublicKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#9)]
 [!code-vb[CryptoWalkThru#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#9)]  
  
## <a name="getting-a-private-key"></a><span data-ttu-id="7cfcb-197">개인 키 가져오기</span><span class="sxs-lookup"><span data-stu-id="7cfcb-197">Getting a Private Key</span></span>  
 <span data-ttu-id="7cfcb-198">이 작업은 키 컨테이너 이름을 `Create Keys` 단추를 사용하여 만든 키의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-198">This task sets the key container name to the name of the key created by using the `Create Keys` button.</span></span> <span data-ttu-id="7cfcb-199">키 컨테이너는 private 매개 변수가 있는 전체 키 쌍을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-199">The key container will contain the full key pair with private parameters.</span></span>  
  
 <span data-ttu-id="7cfcb-200">이 작업은 Alice가 개인 키를 사용하여 Bob이 암호화한 파일을 암호 해독하는 시나리오를 시뮬레이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-200">This task simulates the scenario of Alice using her private key to decrypt files encrypted by Bob.</span></span>  
  
 <span data-ttu-id="7cfcb-201">`Get Private Key` 단추(`buttonGetPrivateKey_Click`)에 대한 `Click` 이벤트 처리기로 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-201">Add the following code as the `Click` event handler for the `Get Private Key` button (`buttonGetPrivateKey_Click`).</span></span>  
  
 [!code-csharp[CryptoWalkThru#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CryptoWalkThru/cs/Form1.cs#7)]
 [!code-vb[CryptoWalkThru#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CryptoWalkThru/vb/Form1.vb#7)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="7cfcb-202">응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="7cfcb-202">Testing the Application</span></span>  
 <span data-ttu-id="7cfcb-203">응용 프로그램을 빌드한 후 다음과 같은 테스트 시나리오를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-203">After you have built the application, perform the following testing scenarios.</span></span>  
  
#### <a name="to-create-keys-encrypt-and-decrypt"></a><span data-ttu-id="7cfcb-204">키를 만들고 암호화 및 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="7cfcb-204">To create keys, encrypt, and decrypt</span></span>  
  
1.  <span data-ttu-id="7cfcb-205">`Create Keys` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-205">Click the `Create Keys` button.</span></span> <span data-ttu-id="7cfcb-206">레이블이 키 이름을 표시하고 전체 키 쌍임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-206">The label displays the key name and shows that it is a full key pair.</span></span>  
  
2.  <span data-ttu-id="7cfcb-207">`Export Public Key` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-207">Click the `Export Public Key` button.</span></span> <span data-ttu-id="7cfcb-208">공개 키 매개 변수를 내보내는 경우 현재 키가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-208">Note that exporting the public key parameters does not change the current key.</span></span>  
  
3.  <span data-ttu-id="7cfcb-209">`Encrypt File` 단추를 클릭하고 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-209">Click the `Encrypt File` button and select a file.</span></span>  
  
4.  <span data-ttu-id="7cfcb-210">`Decrypt File` 단추를 클릭하고 방금 암호화한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-210">Click the `Decrypt File` button and select the file just encrypted.</span></span>  
  
5.  <span data-ttu-id="7cfcb-211">방금 암호 해독한 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-211">Examine the file just decrypted.</span></span>  
  
6.  <span data-ttu-id="7cfcb-212">응용 프로그램을 닫고 다음 시나리오에서 지속형 키 컨테이너 검색을 테스트하기 위해 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-212">Close the application and restart it to test retrieving persisted key containers in the next scenario.</span></span>  
  
#### <a name="to-encrypt-using-the-public-key"></a><span data-ttu-id="7cfcb-213">공개 키를 사용하여 암호화하려면</span><span class="sxs-lookup"><span data-stu-id="7cfcb-213">To encrypt using the public key</span></span>  
  
1.  <span data-ttu-id="7cfcb-214">`Import Public Key` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-214">Click the `Import Public Key` button.</span></span> <span data-ttu-id="7cfcb-215">레이블이 키 이름을 표시하고 public 전용임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-215">The label displays the key name and shows that it is public only.</span></span>  
  
2.  <span data-ttu-id="7cfcb-216">`Encrypt File` 단추를 클릭하고 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-216">Click the `Encrypt File` button and select a file.</span></span>  
  
3.  <span data-ttu-id="7cfcb-217">`Decrypt File` 단추를 클릭하고 방금 암호화한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-217">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="7cfcb-218">암호 해독하려면 개인 키가 있어야 하므로 이 작업은 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-218">This will fail because you must have the private key to decrypt.</span></span>  
  
 <span data-ttu-id="7cfcb-219">이 시나리오에서는 다른 사용자를 위해 파일을 암호화할 공개 키만 있는 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-219">This scenario demonstrates having only the public key to encrypt a file for another person.</span></span> <span data-ttu-id="7cfcb-220">일반적으로 해당 사용자는 공개 키만 제공하고 암호 해독을 위한 개인 키는 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-220">Typically that person would give you only the public key and withhold the private key for decryption.</span></span>  
  
#### <a name="to-decrypt-using-the-private-key"></a><span data-ttu-id="7cfcb-221">개인 키를 사용하여 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="7cfcb-221">To decrypt using the private key</span></span>  
  
1.  <span data-ttu-id="7cfcb-222">`Get Private Key` 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-222">Click the `Get Private Key` button.</span></span> <span data-ttu-id="7cfcb-223">레이블이 키 이름을 표시하고 전체 키 쌍인지 여부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-223">The label displays the key name and shows whether it is the full key pair.</span></span>  
  
2.  <span data-ttu-id="7cfcb-224">`Decrypt File` 단추를 클릭하고 방금 암호화한 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-224">Click the `Decrypt File` button and select the file just encrypted.</span></span> <span data-ttu-id="7cfcb-225">암호 해독을 위한 전체 키 쌍이 있으므로 이 작업은 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="7cfcb-225">This will be successful because you have the full key pair to decrypt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cfcb-226">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7cfcb-226">See Also</span></span>  
 [<span data-ttu-id="7cfcb-227">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="7cfcb-227">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)

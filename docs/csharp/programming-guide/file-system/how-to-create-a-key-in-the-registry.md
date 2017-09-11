---
title: "방법: 레지스트리에 키 만들기(Visual C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 96d34df3314494fc96ad8b55d7462b67dcc7bd72
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-key-in-the-registry-visual-c"></a><span data-ttu-id="66023-102">방법: 레지스트리에 키 만들기(Visual C#)</span><span class="sxs-lookup"><span data-stu-id="66023-102">How to: Create a Key In the Registry (Visual C#)</span></span>
<span data-ttu-id="66023-103">이 예제에서는 현재 사용자의 레지스트리, "Names" 키 아래에 "Name" 및 "Isabella" 값 쌍을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="66023-103">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="66023-104">예제</span><span class="sxs-lookup"><span data-stu-id="66023-104">Example</span></span>  
  
```  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="66023-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="66023-105">Compiling the Code</span></span>  
  
-   <span data-ttu-id="66023-106">코드를 복사하고 콘솔 응용 프로그램의 `Main` 메서드에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="66023-106">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
-   <span data-ttu-id="66023-107">`Names` 매개 변수를 레지스트리의 HKEY_CURRENT_USER 노드 바로 아래에 있는 키 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="66023-107">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
-   <span data-ttu-id="66023-108">`Name` 매개 변수를 Names 노드 바로 아래에 있는 값 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="66023-108">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="66023-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="66023-109">Robust Programming</span></span>  
 <span data-ttu-id="66023-110">레지스트리 구조를 검사하여 키에 적합한 위치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="66023-110">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="66023-111">예를 들어 현재 사용자의 소프트웨어 키를 열고 회사 이름으로 키를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66023-111">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="66023-112">그런 다음 회사 키에 레지스트리 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="66023-112">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="66023-113">다음 조건에서 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66023-113">The following conditions might cause an exception:</span></span>  
  
-   <span data-ttu-id="66023-114">키 이름이 null인 경우</span><span class="sxs-lookup"><span data-stu-id="66023-114">The name of the key is null.</span></span>  
  
-   <span data-ttu-id="66023-115">사용자에게 레지스트리 키를 만들 수 있는 권한이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="66023-115">The user does not have permissions to create registry keys.</span></span>  
  
-   <span data-ttu-id="66023-116">키 이름이 255자 제한을 초과하는 경우</span><span class="sxs-lookup"><span data-stu-id="66023-116">The key name exceeds the 255-character limit.</span></span>  
  
-   <span data-ttu-id="66023-117">키가 닫힌 경우</span><span class="sxs-lookup"><span data-stu-id="66023-117">The key is closed.</span></span>  
  
-   <span data-ttu-id="66023-118">레지스트리 키가 읽기 전용인 경우</span><span class="sxs-lookup"><span data-stu-id="66023-118">The registry key is read-only.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="66023-119">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="66023-119">.NET Framework Security</span></span>  
 <span data-ttu-id="66023-120">로컬 컴퓨터(`Microsoft.Win32.Registry.LocalMachine`)보다 사용자 폴더(`Microsoft.Win32.Registry.CurrentUser`)에 데이터를 쓰는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="66023-120">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="66023-121">레지스트리 값을 만들 때 해당 값이 이미 있는 경우 수행할 작업을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66023-121">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="66023-122">다른 악성 프로세스에서 값을 이미 만들고 액세스했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66023-122">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="66023-123">레지스트리 값에 데이터를 넣으면 다른 프로세스에서 해당 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66023-123">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="66023-124">이를 방지하려면 `Overload:Microsoft.Win32.RegistryKey.GetValue`</span><span class="sxs-lookup"><span data-stu-id="66023-124">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="66023-125">메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="66023-125">method.</span></span> <span data-ttu-id="66023-126">키가 아직 없는 경우 null이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="66023-126">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="66023-127">레지스트리 키가 ACL(액세스 제어 목록)로 보호된 경우에도 암호 등을 레지스트리에 일반 텍스트로 저장하는 것은 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66023-127">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66023-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66023-128">See Also</span></span>  
 <span data-ttu-id="66023-129"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="66023-129"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="66023-130">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="66023-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="66023-131">[파일 시스템 및 레지스트리(C# 프로그래밍 가이드)](../../../csharp/programming-guide/file-system/index.md) </span><span class="sxs-lookup"><span data-stu-id="66023-131">[File System and the Registry (C# Programming Guide)](../../../csharp/programming-guide/file-system/index.md) </span></span>  
 [<span data-ttu-id="66023-132">C#을 사용하여 레지스트리에서 읽기, 쓰기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="66023-132">Read, write and delete from the registry with C#</span></span>](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)


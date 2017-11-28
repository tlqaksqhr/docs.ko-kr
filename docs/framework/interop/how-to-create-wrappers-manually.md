---
title: "방법: 수동으로 래퍼 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: wrappers, creating manually
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19f605203a79f8435d414fb3c2eb7041c9824640
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-wrappers-manually"></a><span data-ttu-id="85c1e-102">방법: 수동으로 래퍼 만들기</span><span class="sxs-lookup"><span data-stu-id="85c1e-102">How to: Create Wrappers Manually</span></span>
<span data-ttu-id="85c1e-103">관리 소스 코드에서 COM 형식을 수동으로 선언하도록 결정할 경우 기존 IDL(Interface Definition Language) 파일 또는 형식 라이브러리에서 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-103">If you decide to declare COM types manually in managed source code, the best place to start is with an existing Interface Definition Language (IDL) file or type library.</span></span> <span data-ttu-id="85c1e-104">IDL 파일이 없거나 형식 라이브러리 파일을 생성할 수 없으면 관리되는 선언을 만들고 결과 어셈블리를 형식 라이브러리에 내보내는 방식으로 COM 형식을 시뮬레이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-104">When you do not have the IDL file or cannot generate a type library file, you can simulate the COM types by creating managed declarations and exporting the resulting assembly to a type library.</span></span>  
  
### <a name="to-simulate-com-types-from-managed-source"></a><span data-ttu-id="85c1e-105">관리되는 소스에서 COM 형식을 시뮬레이트하려면</span><span class="sxs-lookup"><span data-stu-id="85c1e-105">To simulate COM types from managed source</span></span>  
  
1.  <span data-ttu-id="85c1e-106">CLS(공용 언어 사양)를 준수하는 언어로 형식을 선언하고 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-106">Declare the types in a language that is compliant with the Common Language Specification (CLS) and compile the file.</span></span>  
  
2.  <span data-ttu-id="85c1e-107">[형식 라이브러리 내보내기(Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)를 사용하여 형식이 포함된 어셈블리를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-107">Export the assembly containing the types with the [Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
3.  <span data-ttu-id="85c1e-108">내보낸 COM 형식 라이브러리를 기반으로 COM 지향 관리되는 형식을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-108">Use the exported COM type library as a basis for declaring COM-oriented managed types.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-rcw"></a><span data-ttu-id="85c1e-109">RCW(런타임 호출 가능 래퍼)를 만들려면</span><span class="sxs-lookup"><span data-stu-id="85c1e-109">To create a runtime callable wrapper (RCW)</span></span>  
  
1.  <span data-ttu-id="85c1e-110">IDL 파일 또는 형식 라이브러리 파일이 있다고 가정하고 사용자 지정 RCW에 포함할 클래스와 인터페이스를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-110">Assuming that you have an IDL file or type library file, decide which classes and interfaces you want to include in the custom RCW.</span></span> <span data-ttu-id="85c1e-111">응용 프로그램에서 직접적으로나 간접적으로 사용하지 않을 형식을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-111">You can exclude any types that you do not intend to use directly or indirectly in your application.</span></span>  
  
2.  <span data-ttu-id="85c1e-112">소스 파일을 CLS 규격 언어로 만들고 형식을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-112">Create a source file in a CLS-compliant language and declare the types.</span></span> <span data-ttu-id="85c1e-113">가져오기 변환 프로세스에 대한 자세한 내용은 [형식 라이브러리와 어셈블리 간 변환 요약](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85c1e-113">See [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958) for a complete description of the import conversion process.</span></span> <span data-ttu-id="85c1e-114">사실상 사용자 지정 RCW를 만들면 [형식 라이브러리 가져오기(Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)에서 제공된 형식 변환 활동을 수동으로 수행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-114">Effectively, when you create a custom RCW, you are manually performing the type conversion activity provided by the [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="85c1e-115">이 섹션 뒤에 나오는 예제에서는 IDL 또는 형식 라이브러리 파일에 있는 형식과 C# 코드에서 이 형식에 해당하는 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-115">The example in the next section shows types in an IDL or type library file and their corresponding types in C# code.</span></span>  
  
3.  <span data-ttu-id="85c1e-116">선언이 완료되면 다른 관리 소스 코드를 컴파일할 때 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-116">When the declarations are complete, compile the file as you compile any other managed source code.</span></span>  
  
4.  <span data-ttu-id="85c1e-117">Tlbimp.exe로 가져온 형식처럼 일부 형식에는 코드에 직접 추가할 수 있는 추가적인 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-117">As with the types imported with Tlbimp.exe, some require additional information, which you can add directly to your code.</span></span> <span data-ttu-id="85c1e-118">자세한 내용은 [방법: interop 어셈블리 편집](http://msdn.microsoft.com/en-us/16aacb20-2269-42bf-a812-b6a7df17e277)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85c1e-118">For details, see [How to: Edit Interop Assemblies](http://msdn.microsoft.com/en-us/16aacb20-2269-42bf-a812-b6a7df17e277).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85c1e-119">예제</span><span class="sxs-lookup"><span data-stu-id="85c1e-119">Example</span></span>  
 <span data-ttu-id="85c1e-120">다음 코드에서는 IDL의 `ISATest` 인터페이스와 `SATest` 클래스 및 C# 소스 코드에서 이들 항목에 해당하는 형식의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85c1e-120">The following code shows an example of the `ISATest` interface and `SATest` class in IDL and the corresponding types in C# source code.</span></span>  
  
 <span data-ttu-id="85c1e-121">**IDL 또는 형식 라이브러리 파일**</span><span class="sxs-lookup"><span data-stu-id="85c1e-121">**IDL or type library file**</span></span>  
  
```  
 [  
object,  
uuid(40A8C65D-2448-447A-B786-64682CBEF133),  
dual,  
helpstring("ISATest Interface"),  
pointer_default(unique)  
 ]  
interface ISATest : IDispatch  
 {  
[id(1), helpstring("method InSArray")]   
HRESULT InSArray([in] SAFEARRAY(int) *ppsa, [out,retval] int *pSum);  
 };  
 [  
uuid(116CCA1E-7E39-4515-9849-90790DA6431E),  
helpstring("SATest Class")  
 ]  
coclass SATest  
 {  
  [default] interface ISATest;  
 };  
```  
  
 <span data-ttu-id="85c1e-122">**관리 소스 코드의 래퍼**</span><span class="sxs-lookup"><span data-stu-id="85c1e-122">**Wrapper in managed source code**</span></span>  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
using System.Runtime.CompilerServices;  
  
[assembly:Guid("E4A992B8-6F5C-442C-96E7-C4778924C753")]  
[assembly:ImportedFromTypeLib("SAServerLib")]  
namespace SAServer  
{  
 [ComImport]  
 [Guid("40A8C65D-2448-447A-B786-64682CBEF133")]  
 [TypeLibType(TypeLibTypeFlags.FLicensed)]  
 public interface ISATest  
 {  
  [DispId(1)]  
  //[MethodImpl(MethodImplOptions.InternalCall,  
  // MethodCodeType=MethodCodeType.Runtime)]  
  int InSArray( [MarshalAs(UnmanagedType.SafeArray,  
      SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }   
 [ComImport]  
 [Guid("116CCA1E-7E39-4515-9849-90790DA6431E")]  
 [ClassInterface(ClassInterfaceType.None)]  
 [TypeLibType(TypeLibTypeFlags.FCanCreate)]  
 public class SATest : ISATest  
 {  
  [DispId(1)]  
  [MethodImpl(MethodImplOptions.InternalCall,   
  MethodCodeType=MethodCodeType.Runtime)]  
  extern int ISATest.InSArray( [MarshalAs(UnmanagedType.SafeArray,   
  SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="85c1e-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85c1e-123">See Also</span></span>  
 [<span data-ttu-id="85c1e-124">런타임 호출 가능 래퍼 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="85c1e-124">Customizing Runtime Callable Wrappers</span></span>](http://msdn.microsoft.com/en-us/4652beaf-77d0-4f37-9687-ca193288c0be)  
 [<span data-ttu-id="85c1e-125">COM 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="85c1e-125">COM Data Types</span></span>](http://msdn.microsoft.com/en-us/f93ae35d-a416-4218-8700-c8218cc90061)  
 [<span data-ttu-id="85c1e-126">방법: Interop 어셈블리 편집</span><span class="sxs-lookup"><span data-stu-id="85c1e-126">How to: Edit Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/16aacb20-2269-42bf-a812-b6a7df17e277)  
 [<span data-ttu-id="85c1e-127">형식 라이브러리를 어셈블리로 변환 요약</span><span class="sxs-lookup"><span data-stu-id="85c1e-127">Type Library to Assembly Conversion Summary</span></span>](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958)  
 [<span data-ttu-id="85c1e-128">Tlbimp.exe(형식 라이브러리 가져오기)</span><span class="sxs-lookup"><span data-stu-id="85c1e-128">Tlbimp.exe (Type Library Importer)</span></span>](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 [<span data-ttu-id="85c1e-129">Tlbexp.exe(형식 라이브러리 내보내기)</span><span class="sxs-lookup"><span data-stu-id="85c1e-129">Tlbexp.exe (Type Library Exporter)</span></span>](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)

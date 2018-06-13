---
title: '방법: 엔터티를 serialize 가능하도록 만들기'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: c3b877df9707e0f98dbc2238d910842649def07f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354948"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="e7e8a-102">방법: 엔터티를 serialize 가능하도록 만들기</span><span class="sxs-lookup"><span data-stu-id="e7e8a-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="e7e8a-103">코드를 생성할 때 엔터티를 serialize 가능하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e8a-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="e7e8a-104">엔터티 클래스는 <xref:System.Runtime.Serialization.DataContractAttribute> 특성으로 데코레이팅되고 열은 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성으로 데코레이팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7e8a-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="e7e8a-105">Visual Studio를 사용 하 여 개발자가 사용할 수는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 이 목적을 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e8a-105">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for this purpose.</span></span>  
  
 <span data-ttu-id="e7e8a-106">SQLMetal 명령줄 도구를 사용 하는 경우는 **/serialization** 옵션과 함께 `unidirectional` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="e7e8a-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="e7e8a-107">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7e8a-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7e8a-108">예제</span><span class="sxs-lookup"><span data-stu-id="e7e8a-108">Example</span></span>  
 <span data-ttu-id="e7e8a-109">다음 SQLMetal 명령줄에서는 serialize 가능한 엔터티가 있는 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e8a-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7e8a-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7e8a-110">See Also</span></span>  
 [<span data-ttu-id="e7e8a-111">serialization</span><span class="sxs-lookup"><span data-stu-id="e7e8a-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)  
 [<span data-ttu-id="e7e8a-112">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="e7e8a-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)

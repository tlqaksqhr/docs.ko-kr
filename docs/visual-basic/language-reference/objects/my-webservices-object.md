---
title: My.WebServices 개체 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: 7ae99bec5797591e53c6c77f5d9f88589352104c
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2018
ms.locfileid: "40240348"
---
# <a name="mywebservices-object"></a><span data-ttu-id="4a274-102">My.WebServices 개체</span><span class="sxs-lookup"><span data-stu-id="4a274-102">My.WebServices Object</span></span>
<span data-ttu-id="4a274-103">만들기 및 현재 프로젝트에서 참조 하는 각 XML 웹 서비스의 단일 인스턴스 액세스에 대 한 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-103">Provides properties for creating and accessing a single instance of each XML Web service referenced by the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a274-104">설명</span><span class="sxs-lookup"><span data-stu-id="4a274-104">Remarks</span></span>  
 <span data-ttu-id="4a274-105">`My.WebServices` 개체는 현재 프로젝트에서 참조하는 각 웹 서비스의 인스턴스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-105">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="4a274-106">필요에 따라 각 인스턴스가 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-106">Each instance is instantiated on demand.</span></span> <span data-ttu-id="4a274-107">`My.WebServices` 개체의 속성을 통해 이러한 웹 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-107">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="4a274-108">속성 이름은 속성이 액세스하는 웹 서비스의 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-108">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="4a274-109"><xref:System.Web.Services.Protocols.SoapHttpClientProtocol>에서 상속되는 모든 클래스는 웹 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-109">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span> <span data-ttu-id="4a274-110">웹 서비스 프로젝트에 추가 하는 방법에 대 한 내용은 [응용 프로그램 웹 서비스 액세스](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-110">For information about adding Web services to a project, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="4a274-111">`My.WebServices` 개체는 현재 프로젝트와 연결 된 웹 서비스만 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-111">The `My.WebServices` object exposes only the Web services associated with the current project.</span></span> <span data-ttu-id="4a274-112">참조 되는 Dll에 선언 된 웹 서비스에 대 한 액세스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-112">It does not provide access to Web services declared in referenced DLLs.</span></span> <span data-ttu-id="4a274-113">폼의 웹 서비스의 정규화 된 이름을 사용 해야 하는 DLL을 제공 하는 웹 서비스에 액세스 하려면 *DllName*. *WebServiceName*합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-113">To access a Web service that a DLL provides, you must use the qualified name of the Web service, in the form *DllName*.*WebServiceName*.</span></span> <span data-ttu-id="4a274-114">자세한 내용은 [응용 프로그램 웹 서비스 액세스](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-114">For more information, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="4a274-115">개체 및 해당 속성 웹 응용 프로그램에 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="4a274-115">The object and its properties are not available for Web applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4a274-116">속성</span><span class="sxs-lookup"><span data-stu-id="4a274-116">Properties</span></span>  
 <span data-ttu-id="4a274-117">각 속성은 `My.WebServices` 개체는 현재 프로젝트에서 참조 하는 웹 서비스 인스턴스에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-117">Each property of the `My.WebServices` object provides access to an instance of a Web service referenced by the current project.</span></span> <span data-ttu-id="4a274-118">속성의 이름은 속성이 액세스 하는 웹 서비스의 이름과 동일 하 고 속성 형식은 웹 서비스의 형식과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-118">The name of the property is the same as the name of the Web service that the property accesses, and the property type is the same as the Web service's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a274-119">이름이 충돌할 경우 웹 서비스 액세스에 대 한 속성 이름이 *RootNamespace*_*Namespace*\_*ServiceName*합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-119">If there is a name collision, the property name for accessing a Web service is *RootNamespace*_*Namespace*\_*ServiceName*.</span></span> <span data-ttu-id="4a274-120">예를 들어 라는 두 개의 웹 서비스가 `Service1`합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-120">For example, consider two Web services named `Service1`.</span></span> <span data-ttu-id="4a274-121">루트 네임 스페이스의 경우 이러한 서비스 중 하나 `WindowsApplication1` 에 네임 스페이스 `Namespace1`를 사용 하 여 서비스에 액세스할 수 있습니다 `My.WebServices.WindowsApplication1_Namespace1_Service1`합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-121">If one of these services is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that service by using `My.WebServices.WindowsApplication1_Namespace1_Service1`.</span></span>  
  
 <span data-ttu-id="4a274-122">처음으로 액세스 하면 중 하나는 `My.WebServices` 개체의 속성을 웹 서비스의 새 인스턴스를 만들고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-122">When you first access one of the `My.WebServices` object's properties, it creates a new instance of the Web service and stores it.</span></span> <span data-ttu-id="4a274-123">해당 속성의 후속 액세스는 웹 서비스의 해당 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-123">Subsequent accesses of that property return that instance of the Web service.</span></span>  
  
 <span data-ttu-id="4a274-124">할당 하 여 웹 서비스의 삭제할 수 있습니다 `Nothing` 해당 웹 서비스에 대 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-124">You can dispose of a Web service by assigning `Nothing` to the property for that Web service.</span></span> <span data-ttu-id="4a274-125">속성 setter 할당 `Nothing` 저장 된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-125">The property setter assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="4a274-126">이외의 모든 값을 할당 하는 경우 `Nothing` 속성에 setter throw는 <xref:System.ArgumentException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-126">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="4a274-127">속성이 있는지 여부를 테스트할 수 있습니다 합니다 `My.WebServices` 개체를 사용 하 여 웹 서비스의 인스턴스를 저장 합니다 `Is` 또는 `IsNot` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-127">You can test whether a property of the `My.WebServices` object stores an instance of the Web service by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="4a274-128">이러한 연산자를 사용 하 여 속성의 값이 인지 확인 하려면 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-128">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a274-129">일반적으로 `Is` 또는 `IsNot` 연산자의 비교를 수행 하는 속성의 값을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-129">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="4a274-130">그러나 현재 저장 하는 경우 `Nothing`, 속성이 웹 서비스의 새 인스턴스를 만들고 다음 해당 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-130">However, if the property currently stores `Nothing`, the property creates a new instance of the Web service and then returns that instance.</span></span> <span data-ttu-id="4a274-131">Visual Basic 컴파일러의 속성을 처리 하는 반면 합니다 `My.WebServices` 하며 특히 개체를 `Is` 또는 `IsNot` 해당 값을 변경 하지 않고 속성의 상태를 확인 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-131">However, the Visual Basic compiler treats the properties of the `My.WebServices` object specially, and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a274-132">예</span><span class="sxs-lookup"><span data-stu-id="4a274-132">Example</span></span>  
 <span data-ttu-id="4a274-133">이 예제에서는 호출을 `FahrenheitToCelsius` 메서드는 `TemperatureConverter` XML 웹 서비스 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-133">This example calls the `FahrenheitToCelsius` method of the `TemperatureConverter` XML Web service, and returns the result.</span></span>  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 <span data-ttu-id="4a274-134">이 예제가 작동 하려면 프로젝트가 라는 웹 서비스를 참조 해야 합니다 `Converter`에 해당 웹 서비스를 노출 해야 하 고는 `ConvertTemperature` 메서드.</span><span class="sxs-lookup"><span data-stu-id="4a274-134">For this example to work, your project must reference a Web service named `Converter`, and that Web service must expose the `ConvertTemperature` method.</span></span> <span data-ttu-id="4a274-135">자세한 내용은 [응용 프로그램 웹 서비스 액세스](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-135">For more information, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).</span></span>  
  
 <span data-ttu-id="4a274-136">이 코드는 웹 응용 프로그램 프로젝트에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a274-136">This code does not work in a Web application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a274-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a274-137">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="4a274-138">프로젝트 형식에 따라 가용성</span><span class="sxs-lookup"><span data-stu-id="4a274-138">Availability by Project Type</span></span>  
  
|<span data-ttu-id="4a274-139">프로젝트 형식</span><span class="sxs-lookup"><span data-stu-id="4a274-139">Project type</span></span>|<span data-ttu-id="4a274-140">사용 가능</span><span class="sxs-lookup"><span data-stu-id="4a274-140">Available</span></span>|  
|---|---|  
|<span data-ttu-id="4a274-141">Windows 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="4a274-141">Windows Application</span></span>|<span data-ttu-id="4a274-142">**예**</span><span class="sxs-lookup"><span data-stu-id="4a274-142">**Yes**</span></span>|  
|<span data-ttu-id="4a274-143">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="4a274-143">Class Library</span></span>|<span data-ttu-id="4a274-144">**예**</span><span class="sxs-lookup"><span data-stu-id="4a274-144">**Yes**</span></span>|  
|<span data-ttu-id="4a274-145">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="4a274-145">Console Application</span></span>|<span data-ttu-id="4a274-146">**예**</span><span class="sxs-lookup"><span data-stu-id="4a274-146">**Yes**</span></span>|  
|<span data-ttu-id="4a274-147">Windows 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="4a274-147">Windows Control Library</span></span>|<span data-ttu-id="4a274-148">**예**</span><span class="sxs-lookup"><span data-stu-id="4a274-148">**Yes**</span></span>|  
|<span data-ttu-id="4a274-149">웹 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="4a274-149">Web Control Library</span></span>|<span data-ttu-id="4a274-150">**예**</span><span class="sxs-lookup"><span data-stu-id="4a274-150">**Yes**</span></span>|  
|<span data-ttu-id="4a274-151">Windows 서비스</span><span class="sxs-lookup"><span data-stu-id="4a274-151">Windows Service</span></span>|<span data-ttu-id="4a274-152">**예**</span><span class="sxs-lookup"><span data-stu-id="4a274-152">**Yes**</span></span>|  
|<span data-ttu-id="4a274-153">웹 사이트</span><span class="sxs-lookup"><span data-stu-id="4a274-153">Web Site</span></span>|<span data-ttu-id="4a274-154">아니요</span><span class="sxs-lookup"><span data-stu-id="4a274-154">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a274-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a274-155">See Also</span></span>  
 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>  
 <xref:System.ArgumentException>  
 [<span data-ttu-id="4a274-156">응용 프로그램 웹 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="4a274-156">Accessing Application Web Services</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)

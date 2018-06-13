---
title: '방법: ServiceContractGenerator에 대한 확장명 쓰기'
ms.date: 03/30/2017
ms.assetid: 876ca823-bd16-4bdf-9e0f-02092df90e51
ms.openlocfilehash: 43105553739e104ab862b3be3cf2082fbf6d499f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488662"
---
# <a name="how-to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="a17f5-102">방법: ServiceContractGenerator에 대한 확장명 쓰기</span><span class="sxs-lookup"><span data-stu-id="a17f5-102">How to: Write an Extension for the ServiceContractGenerator</span></span>
<span data-ttu-id="a17f5-103">이 항목에서는 <xref:System.ServiceModel.Description.ServiceContractGenerator>에 대한 확장을 쓰는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-103">This topic describes how to write an extension for the <xref:System.ServiceModel.Description.ServiceContractGenerator>.</span></span> <span data-ttu-id="a17f5-104">이 작업을 수행하려면 작업 동작에 <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> 인터페이스를 구현하거나 계약 동작에 <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-104">This can be done by implementing the <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> interface on an operation behavior or implementing the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span> <span data-ttu-id="a17f5-105">다음 항목에서는 계약 동작에서 <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> 인터페이스를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-105">This topic shows how to implement the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span>  
  
 <span data-ttu-id="a17f5-106"><xref:System.ServiceModel.Description.ServiceContractGenerator>는 <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription> 및 <xref:System.ServiceModel.Channels.Binding> 인스턴스에서 서비스 계약, 클라이언트 형식 및 클라이언트 구성을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-106">The <xref:System.ServiceModel.Description.ServiceContractGenerator> generates service contracts, client types, and client configurations from <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances.</span></span> <span data-ttu-id="a17f5-107">일반적으로 서비스 메타데이터에서 <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription> 및 <xref:System.ServiceModel.Channels.Binding> 인스턴스를 가져온 다음 이러한 인스턴스를 사용하여 서비스를 호출할 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-107">Typically, you import <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances from service metadata and then use these instances to generate code to call the service.</span></span> <span data-ttu-id="a17f5-108">이 예제에서 <xref:System.ServiceModel.Description.IWsdlImportExtension> 구현은 생성된 코드에 주석을 생성하기 위해 WSDL 주석을 처리한 다음 가져온 계약에 코드 생성 확장을 추가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-108">In this example, an <xref:System.ServiceModel.Description.IWsdlImportExtension> implementation is used to process WSDL annotations and then add code generation extensions to the imported contracts to generate comments on the generated code.</span></span>  
  
### <a name="to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="a17f5-109">ServiceContractGenerator에 대한 확장을 쓰려면</span><span class="sxs-lookup"><span data-stu-id="a17f5-109">To write an extension for the ServiceContractGenerator</span></span>  
  
1.  <span data-ttu-id="a17f5-110"><xref:System.ServiceModel.Description.IServiceContractGenerationExtension>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-110">Implement <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="a17f5-111">생성된 서비스 계약을 수정하려면 <xref:System.ServiceModel.Description.ServiceContractGenerationContext> 메서드로 전달된 <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-111">To modify the generated service contract, use the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> instance passed into the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> method.</span></span>  
  
    ```  
    public void GenerateContract(ServiceContractGenerationContext context)  
    {  
        Console.WriteLine("In generate contract.");  
    context.ContractType.Comments.AddRange(Formatter.FormatComments(commentText));  
    }  
    ```  
  
2.  <span data-ttu-id="a17f5-112">같은 클래스에서 <xref:System.ServiceModel.Description.IWsdlImportExtension>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-112">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension> on the same class.</span></span> <span data-ttu-id="a17f5-113"><xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> 메서드는 가져온 <xref:System.ServiceModel.Description.ContractDescription> 인스턴스에 코드 생성 확장을 추가하여 특정 WSDL 확장(이 경우 WSDL 주석)을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-113">The <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> method can process a specific WSDL extension (WSDL annotations in this case) by adding a code generation extension to the imported <xref:System.ServiceModel.Description.ContractDescription> instance.</span></span>  
  
    ```  
    public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)  
       {  
                // Contract documentation  
             if (context.WsdlPortType.Documentation != null)  
             {  
                    context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));  
             }  
             // Operation documentation  
             foreach (Operation operation in context.WsdlPortType.Operations)  
             {  
                if (operation.Documentation != null)  
                {  
                   OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);  
                   if (operationDescription != null)  
                   {  
                            operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));  
                   }  
                }  
             }  
          }  
          public void BeforeImport(ServiceDescriptionCollection wsdlDocuments, XmlSchemaSet xmlSchemas, ICollection<XmlElement> policy)   
            {  
                Console.WriteLine("BeforeImport called.");  
            }  
  
          public void ImportEndpoint(WsdlImporter importer, WsdlEndpointConversionContext context)   
            {  
                Console.WriteLine("ImportEndpoint called.");  
            }  
    ```  
  
3.  <span data-ttu-id="a17f5-114">클라이언트 구성에 WSDL 가져오기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-114">Add the WSDL importer to your client configuration.</span></span>  
  
    ```xml  
    <metadata>  
      <wsdlImporters>  
        <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
      </wsdlImporters>  
    </metadata>  
    ```  
  
4.  <span data-ttu-id="a17f5-115">클라이언트 코드에 `MetadataExchangeClient`를 만들고 `GetMetadata`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-115">In the client code, create a `MetadataExchangeClient` and call `GetMetadata`.</span></span>  
  
    ```  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(metadataAddress);  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet metaDocs = mexClient.GetMetadata();  
    ```  
  
5.  <span data-ttu-id="a17f5-116">`WsdlImporter`를 만들고 `ImportAllContracts`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-116">Create a `WsdlImporter` and call `ImportAllContracts`.</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);            System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
6.  <span data-ttu-id="a17f5-117">`ServiceContractGenerator`를 만들고 각 계약에 대한 `GenerateServiceContractType`을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-117">Create a `ServiceContractGenerator` and call `GenerateServiceContractType` for each contract.</span></span>  
  
    ```  
    ServiceContractGenerator generator = new ServiceContractGenerator();  
    foreach (ContractDescription contract in contracts)  
    {  
       generator.GenerateServiceContractType(contract);  
    }  
    if (generator.Errors.Count != 0)  
       throw new Exception("There were errors during code compilation.");  
    ```  
  
7.  <span data-ttu-id="a17f5-118"><xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29>는 <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>을 구현하는 제공된 계약에서 각 계약 동작에 대해 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-118"><xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> is called automatically for each contract behavior on a given contract that implements <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="a17f5-119">그런 다음 이 메서드는 전달된 <xref:System.ServiceModel.Description.ServiceContractGenerationContext>를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-119">This method can then modify the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> passed in.</span></span> <span data-ttu-id="a17f5-120">이 예제에서는 주석이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a17f5-120">In this example comments are added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a17f5-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a17f5-121">See Also</span></span>  
 [<span data-ttu-id="a17f5-122">메타데이터</span><span class="sxs-lookup"><span data-stu-id="a17f5-122">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="a17f5-123">방법: 사용자 지정 WSDL 가져오기</span><span class="sxs-lookup"><span data-stu-id="a17f5-123">How to: Import Custom WSDL</span></span>](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)

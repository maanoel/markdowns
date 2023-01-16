#trabalho
#arquitetura
Data: November 29, 2022 3:43 PM

# Estrutura Operacional

- Pedido
    - Pedido
    - Demanda (talvez seja um domínio por si só, sugestão do Rafael)
    - Cadastro de colaborador (importação de demanda)
    - Economia
- Cartão
    - Navega em operadoras para buscar cartões e saldos
    - Leituras automatizadas
    - Identificação de cartão do colaborador na operadora
    - Relatórios de uso
- Cadastro
    - Cadastro de Linhas (conferir se mescla com Roteirização)
        - Tarifas
    - Cadastro de Linhas - Roteirização
    - Integração de Linhas - Roteirização
    - Divergências/conferência - Roteirização
    - Cadastro de Estações - Roteirização
    - Cadastro de Pedágios - Roteirização
    - Operadora
- Logística
    - Coleta
    - Entrega
    - Recusa
    - Pedido
    - Solicitação (relaciona)
- Implantação
    - Vínculo Operadora x Unidade
    - Configura o grupo econômico
    - Cadastro de Unidades
    - Configura as unidades do grupo econômico
    - Escala
    - Solicitar saldo
- Suporte
    - Autogestão
    - Correção de erros gerados na Terceirização
    - Atendimento de Solicitação
    - Pode cadastrar unidades
    - Pode cadastrar operadora da unidade
    - Solicitar saldo
- Processamento Alelo
    - Importam pedido de processamento de saldo
    - Cadastra código de produto
    - Cadastro de grupo econômico
    - Cadastro de unidades
    - Cadastro de operadora da unidade
    - Solicitam resgate do saldo ABSMob para Alelo
    - Solicitar saldo
- Vale & Mais
    - (a documentar, Gilberto)
- Ônix
    - (a documentar, Bruno, Thamires e Luccas)
- Solicitação
    - Atendimento
    - Pode gerar pedidos
    - Interna ou Externa
    - Vínculo e desvinculo de colaborador na operadora
    - Manutenção de cartões
    - Autosserviço (feito pelo próprio cliente no portal abscard)
- Financeiro
    - Lote de Pagamentos (integração sempre pela totvs)
    - Bs2 emissão de boleto terceirizado (via API)
    - Boletos automatizados
- Administrativo
    - Grupos Econômicos
    - Licenças de Grupos Econômicos
- Comercial
    - (provavelmente será removido, sem funcionalidade sistêmica)
- Automações
    - Autoriza operadoras a serem automatizadas
    - Permite configurar assuntos de automações diversos
    - Registra logs de como a automação está sendo executada

# Produtos

- Gestão de Saldo
- ABSCard Terceirizado
- ABS Rotas
- ABSMob
- Logística
- Vale & Mais (tecnicamente é um TIPO de licença)
- Ônix

---

# Microsserviços

## ABSCard.Domain.User > Usuário, controle de acesso e perfis

- [ ] AccessControlService
- [ ] AccessManagementService
- [ ] PortalAppAuthRequestService
- [ ] AspNetUserService
- [ ] BranchPermissionsService
- [ ] LoginAttemptsService
- [ ] ProfileAccessControlService
- [ ] ProfileBranchService
- [ ] ProfileReportService
- [ ] ProfilesService
- [ ] ProfileUserService
- [ ] UserAuthenticationService
- [ ] UserPermissionService
- [ ] UserProfileService

## ABSCard.Domain.Order > Pedido

- [ ] AccountPeriodService
- [ ] BranchDiscrepancyService
- [ ] DemandFileService
- [ ] DemandRechargeOrderService
- [ ] DemandItemService
- [ ] PendingDemandApproval
- [ ] DiscrepancyService
- [ ] FormRecognizerErrorLogService
- [ ] MonthlyPurchaseScheduleQueryExceptionService (esclarecer)
- [ ] OcrServiceModelService
- [ ] OperatorExportLayoutsService (esclarecer)
- [ ] OperatorExternalCodeService (esclarecer)
- [ ] OperatorLayoutMarkupService
- [ ] OrdemItemService
- [ ] OrderItemsDeletedService
- [ ] PaymentSlipIntegrityValidation
- [ ] PurchaseErrorService
- [ ] RechargeItemDiscrepancyService
- [ ] RechargePaymentAmountService (esclarecer)
- [ ] TransactionPeriodsService (esclarecer)
- [ ] TransactionService
- [ ] OrderManagerService (esclarecer)

## ABSCard.Domain.Employee > Cadastro de Colaborador

- [ ] EmployeeBaseCardService
- [ ] EmployeeBaseEventService
- [ ] EmployeeBaseFareProductVrService
- [ ] EmployeeBaseRideFareService
- [ ] EmployeeBaseService
- [ ] EmployeeEventService
- [ ] JobRoleService (esclarecer)
- [ ] JobVacancyService (esclarecer)
- [ ] TransactionEmployeeBaseDemandService (aqui ou em Pedido?)
- [ ] TransactionWorkStationDemandService (aqui ou em Pedido?)
- [ ] WorkStationUserService
- [ ] WorkStationService
- [ ] VacationService
- [ ] WorkDayService

## ABSCard.Domain.Card > Cartão

- [ ] OperatorDataErrorService
- [ ] OperatorDataRobotEvidencesService
- [ ] OperatorDataService
- [ ] OperatorExtraCardInfoService
- [ ] PendingRechargeRequestService (esclarecer)
- [ ] ScheduleLogService
- [ ] UnusableBalanceService
- [ ] VteFortalezaCycleOutput
- [ ] CardNumberMaskService
- [ ] MultipleCardHandler

## ABSCard.Domain.PublicTransport > Parte da Operadora no 'Cadastro'

- [ ] OperatorFareDiscountService
- [ ] OperatorFareValueService
- [ ] OperatorFaresService
- [ ] OperatorPasswordToInheritService
- [ ] OperatorTaxesService

## ABSCard.Domain.Routing > Roteirização

- [ ] OperatorFareRouteService
- [ ] RoutingIntegrationService
- [ ] RoutingLogService
- [ ] AccountRoutingHistoryService
- [ ] AutomaticFavoriteService
- [ ] GasolineService (esclarecer)
- [ ] RoutingAccountGarageService
- [ ] RoutingConsumptionService
- [ ] RoutingEmployeeIntegrationService
- [ ] RoutingFavoriteLineService
- [ ] RoutingLineFareService
- [ ] RoutingLinePatternService
- [ ] RoutingMetroAgencyService
- [ ] RoutingMetroAlertService
- [ ] RoutingMultipleBranchParameterService
- [ ] RoutingRequestItemErrorService
- [ ] RoutingRequestService
- [ ] RoutingRoadMapFileService
- [ ] RoutingRoadMapLineService
- [ ] RoutingRoadMapPlaceServices
- [ ] RoutingRoadMapReferenceService
- [ ] RoutingRoadMapStopService
- [ ] RoutingRoadMapSummaryService
- [ ] RoutingRouteIntegrationLineService
- [ ] RoutingRouteIntegrationService
- [ ] RoutingRouteStretchStepService
- [ ] RoutingRouteStretchService
- [ ] RoutingRouteService
- [ ] RoutingStationService
- [ ] RoutingStopService
- [ ] RoutingTollValueService
- [ ] RoutingTollService
- [ ] RoutingRankedBranchService

## ABSCard.Domain.Logistics > Logística

- [ ] DeliveryGroupService
- [ ] DeliveryHistoryService
- [ ] DeliveryServicesService
- [ ] DeliverySupplierPaymentHistoryItemsService
- [ ] DeliverySupplierPaymentHistoryService
- [ ] DeliverySupplierService
- [ ] PickupAddressPointService

## ABSCard.Domain.Customer > Implantação / Administrativo (Parte de Grupo Economico e Unidades no 'Cadastro')

- [ ] AccountAddressService
- [ ] AddressBranchService
- [ ] AccountLicenseService
- [ ] BranchParameterService
- [ ] LicenseTypeService
- [ ] PartnerService (esclarecer)
- [ ] ScheduleQueryService

## ABSCard.Domain.PartnerOrder > Processamento Alelo

- [ ] BalanceProcessingFileErrorLogService
- [ ] BalanceProcessingItemService

## ABSCard.Domain.CustomerService > Suporte / Solicitação

- [ ] CloseIncidentIntegration (esclarecer)
- [ ] InteractionService (esclarecer)
- [ ] PaymentIncidentIntegrationService

## ABSCard.Domain.Financial > Financeiro

- [ ] BatchPaymentDefinitionService
- [ ] BatchPaymentIncidentIntegration
- [ ] BatchPaymentIntegrationTovsLog
- [ ] BatchPaymentOrderGroup
- [ ] BatchPaymentOrder
- [ ] BatchPaymentRechargeOrder
- [ ] BillingDataBpoService
- [ ] BillingDataService
- [ ] BS2TokenService
- [ ] PayLotDetailsVrService
- [ ] BpoPayLotService
- [ ] CommercialConditionFeeService (esclarecer)
- [ ] ContractCommercialConditionFeeService (esclarecer)
- [ ] CreditStockService (esclarecer)
- [ ] DemandCommercialConditionFeeService (aqui ou em Pedido?)
- [ ] EmployeeFinancialOperationService
- [ ] FinancialLaunchConditionService (esclarecer)
- [ ] FinancialLaunchLiquidationService (esclarecer)
- [ ] IntegrationTotvsTransactionService
- [ ] TotvsIntegrationInvoiceFilesService
- [ ] TotvsIntegrationInvoiceService
- [ ] TotvsIntegrationXmlService
- [ ] OperatorInvoiceService
- [ ] PayLotDetailsService
- [ ] BilletBankLoggerService (esclarecer)

## ABSCard.Domain.Automation > Automações

- [ ] AutomatedOperatorService
- [ ] CanceledCardRequestService (esclarecer)
- [ ] OrderPurchaseOutputService (aqui mesmo?)
- [ ] RechargePurchaseRequestService
- [ ] RobotVersionService
- [ ] SPTransActiveCardsRequestService
- [ ] SPTransCardsInsideOrdersInputService
- [ ] SPTransCardsInsideOrdersRequestService
- [ ] CanceledCardOutputService (esclarecer)
- [ ] CanceledCardsRequestService (esclarecer)
- [ ] LayoutChangesNotifier (esclarecer)

## ABSCard.Domain.Pat > Pat

- [ ] BeneficiaryPatService
- [ ] BenefitLoadPatService
- [ ] PlacePatService
- [ ] ResponsiblePatService
- [ ] ResponsiblePlacePatService
- [ ] ResponsibleUserPatService
- [ ] RechargeCardPatService (esclarecer)
- [ ] TransactionPatService

## ABSCard.Domain.?? > Vale & Mais (pendente, irá gerar mais domínios)

- [ ] CreateBpoAccountService
- [ ] AffiliateCodeService (esclarecer)
- [ ] AffiliateFareService (esclarecer)
- [ ] AffiliateOperatorFareService (esclarecer)
- [ ] BpoSyncLogService
- [ ] RequestIntegrateBpoService

## ABSCard.Domain.?? > Ônix (pendente, irá gerar mais domínios)

## Esclarecer em qual microsserviço entra

- ApiUserService
- AppBalanceHistoryService
- AppDeletionLogServices
- AppFeedbackService
- AppNotificationService
- AppRescueRequestService
- AppRoutingEvidenceService
- AppSpotlightAccountService
- AppSpotlightFileService
- AppSpotlightService
- AppTransactionEvidenceService
- AppVoucherRedeemService
- AttachmentsBlobFilesService
- AttachmentsFilesService
- BalanceAbsMobCalculator
- CommunicationHolidayApi
- BankRegisterService
- BranchInteractionService
- WsHelper
- CartaoTopService
- CityService
- StateService
- DepartmentService
- DownloadHistoryService
- EconometroEmailHistorieService
- FileService
- ImportErrorService
- IntegrationAccountService
- IntegrationAddressService
- IntegrationHeaderService
- IntegrationInterlocutorService
- InterlocutorService
- LocationService
- MandateBranchsService
- PartnerProductVrService
- PeriodService
- ProductBillingService
- ProspectionContactService
- DevolutionLogHistoryService
- TransactionRemissionService
- ReportRequestService
- ReportService
- ScheduleQueryHistoryService
- ServicesService
- ServiceTemplateMessageAccountService
- ServiceTemplateMessageOperatorService
- ServiceTemplateMessageService
- SMSCodeCenterService
- StatusService
- VersionNewsService
- VrFileReaderService
- ProspectionService
- IntegrationContractService
- IntegrationCommercialConditionFeeService
- Notifier
- PoseidonLogsService
- PoseidonTokenService
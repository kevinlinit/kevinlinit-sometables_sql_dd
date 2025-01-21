create table WF_ONE_LCSL_WYSYGZ
(
    "ACTIVITYID"   varchar(30),
    "TASKTARGETID" varchar(30),
    "PIID"         varchar(50)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_ONE_LCSL_WYSYGZ_IN
(
    "ACTIVITYID"   varchar(30),
    "TASKTARGETID" varchar(30),
    "PIID"         varchar(50)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_ONE_LCSL_WYSYGZ_NOT
(
    "ACTIVITYID"   varchar(30),
    "TASKTARGETID" varchar(30),
    "PIID"         varchar(50)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_SCHDDX_TASK
(
    "TASKID" varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_SCHDDX_TASKHIS
(
    "TASKID" varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TD_ASSIGNSTRATEGY
(
    "ASSIGNSTRATEGYID"   varchar(20) not null constraint "PK_WF_TD_ASSIGNSTRATEGY"
            primary key,
    "ASSIGNSTRATEGYNAME" varchar(50) not null,
    "REMARK"             varchar(200),
    "COMID"              varchar(8)  not null,
    "INSERTTIMEFORHIS"   timestamp,
    "OPERATETIMEFORHIS"  timestamp,
    "UPDATERCODE"        varchar(10)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_TD_ASSIGNSTRATEGY is 'WF_TD_AssignStrategy,分配策略表';

comment on column WF_TD_ASSIGNSTRATEGY."ASSIGNSTRATEGYID" is 'AssignStrategyID,分配策略ID';

comment on column WF_TD_ASSIGNSTRATEGY."ASSIGNSTRATEGYNAME" is 'AssignStrategyName,分配策略名称';

comment on column WF_TD_ASSIGNSTRATEGY."REMARK" is 'Remark,分配策略说明';

comment on column WF_TD_ASSIGNSTRATEGY."COMID" is 'ComId,8位机构号';

comment on column WF_TD_ASSIGNSTRATEGY."INSERTTIMEFORHIS" is 'InsertTimeForHis,插入时间';

comment on column WF_TD_ASSIGNSTRATEGY."OPERATETIMEFORHIS" is 'OperateTimeForHis,更新时间';

comment on column WF_TD_ASSIGNSTRATEGY."UPDATERCODE" is 'UpdaterCode,更新人';


create table WF_TD_INDICATORDIC
(
    "INDICATORID"       varchar(30) not null constraint "PK_WF_TD_INDICATORDIC"
            primary key,
    "INDICATORNAME"     varchar(50),
    "INDICATORTYPE"     varchar(50),
    "METADATAID"        varchar(30),
    "OPERATELOGIC"      varchar(50),
    "COMID"             varchar(8)  not null,
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "UPDATERCODE"       varchar(10),
    "IDXSQL"            varchar(4000)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_TD_INDICATORDIC is 'WF_TD_IndicatorDic,监控指标字典表';

comment on column WF_TD_INDICATORDIC."INDICATORID" is 'IndicatorID,指标ID';

comment on column WF_TD_INDICATORDIC."INDICATORNAME" is 'IndicatorName,指标名称';

comment on column WF_TD_INDICATORDIC."INDICATORTYPE" is 'IndicatorType,指标类别';

comment on column WF_TD_INDICATORDIC."METADATAID" is 'MetadataID,关联元数据ID';

comment on column WF_TD_INDICATORDIC."OPERATELOGIC" is 'OperateLogic,逻辑运算';

comment on column WF_TD_INDICATORDIC."COMID" is 'ComId,8位机构号';

comment on column WF_TD_INDICATORDIC."INSERTTIMEFORHIS" is 'InsertTimeForHis,创建时间';

comment on column WF_TD_INDICATORDIC."OPERATETIMEFORHIS" is 'OperateTimeForHis,更新时间';

comment on column WF_TD_INDICATORDIC."UPDATERCODE" is 'UpdaterCode,更新人';

comment on column WF_TD_INDICATORDIC."IDXSQL" is 'IdxSql,指标运算SQL';


create table WF_TD_METADATADIC
(
    "METADATAID"        varchar(30) not null constraint "PK_WF_TD_METADATADIC"
            primary key,
    "METADATANAME"      varchar(50),
    "METADATATYPE"      varchar(20),
    "METADATAFLAG"      varchar(20),
    "REMARK"            varchar(200),
    "TOPMETADATAID"     varchar(30),
    "TOPMETADATANAME"   varchar(30),
    "COMID"             varchar(8)  not null,
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "UPDATERCODE"       varchar(10)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_TD_METADATADIC is 'WF_TD_MetadataDic,元数据信息表';

comment on column WF_TD_METADATADIC."METADATAID" is 'MetadataID,元数据ID';

comment on column WF_TD_METADATADIC."METADATANAME" is 'MetadataName,元数据名称';

comment on column WF_TD_METADATADIC."METADATATYPE" is 'MetadataType,元数据类型';

comment on column WF_TD_METADATADIC."METADATAFLAG" is 'MetadataFlag,元数据标识';

comment on column WF_TD_METADATADIC."REMARK" is 'Remark,元数据描述说明';

comment on column WF_TD_METADATADIC."TOPMETADATAID" is 'TopMetadataID,父元数据ID';

comment on column WF_TD_METADATADIC."TOPMETADATANAME" is 'TopMetadataName,父元数据名称';

comment on column WF_TD_METADATADIC."COMID" is 'ComId,8位机构号';

comment on column WF_TD_METADATADIC."INSERTTIMEFORHIS" is 'InsertTimeForHis,创建时间';

comment on column WF_TD_METADATADIC."OPERATETIMEFORHIS" is 'OperateTimeForHis,更新时间';

comment on column WF_TD_METADATADIC."UPDATERCODE" is 'UpdaterCode,更新人';


create table WF_TD_VARIABLEDIC
(
    "VARIABLEID"        varchar(30) not null constraint "PK_WF_TD_VARIABLEDIC"
            primary key,
    "VARIABLENAME"      varchar(50),
    "VARIABLETYPE"      varchar(20),
    "VARIABLEFLAG"      varchar(20),
    "REMARK"            varchar(200),
    "COMID"             varchar(8)  not null,
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "UPDATERCODE"       varchar(10),
    "METADATAID"        varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_TD_VARIABLEDIC is 'WF_TD_VariableDic,流程模板变量字典表';

comment on column WF_TD_VARIABLEDIC."VARIABLEID" is 'VariableID,变量ID';

comment on column WF_TD_VARIABLEDIC."VARIABLENAME" is 'VariableName,变量名称';

comment on column WF_TD_VARIABLEDIC."VARIABLETYPE" is 'VariableType,变量类型';

comment on column WF_TD_VARIABLEDIC."VARIABLEFLAG" is 'VariableFlag,变量标识';

comment on column WF_TD_VARIABLEDIC."REMARK" is 'Remark,变量描述说明';

comment on column WF_TD_VARIABLEDIC."COMID" is 'ComId,8位机构号';

comment on column WF_TD_VARIABLEDIC."INSERTTIMEFORHIS" is 'InsertTimeForHis,创建时间';

comment on column WF_TD_VARIABLEDIC."OPERATETIMEFORHIS" is 'OperateTimeForHis,更新时间';

comment on column WF_TD_VARIABLEDIC."UPDATERCODE" is 'UpdaterCode,更新人';

comment on column WF_TD_VARIABLEDIC."METADATAID" is 'MetadataID,关联元数据ID';


create table WF_TEMP_ECIFUPDATETASK
(
    "POLICYNO"  varchar(30),
    "OLDCUSTID" varchar(30),
    "NEWCUSTID" varchar(60),
    "OLDCARID"  varchar(30),
    "NEWCARID"  varchar(30),
    "LICENSENO" varchar(60),
    "PIID"      varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create index "IDX_TEMP_ECIFUPDATETASK_NCAR"
    on WF_TEMP_ECIFUPDATETASK using ubtree ("NEWCARID");

create index "IDX_TEMP_ECIFUPDATETASK_NCUST"
    on WF_TEMP_ECIFUPDATETASK using ubtree ("NEWCUSTID");

create index "IDX_TEMP_ECIFUPDATETASK_PCNO"
    on WF_TEMP_ECIFUPDATETASK using ubtree ("POLICYNO");

create table WF_TEMP_ELECTRICPIN
(
    "INID"              varchar(30),
    "PIID"              varchar(30),
    "TASKID"            varchar(30),
    "TASKTARGETID"      varchar(30),
    "TASKTARGETTYPE"    varchar(1),
    "ACTIVITYID"        varchar(30),
    "ACTIVITYNAME"      varchar(200),
    "REMARK"            varchar(300),
    "DATATYPE"          varchar(4),
    "SALETYPE"          varchar(64),
    "OPERATORCODE"      varchar(10),
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "COMID"             varchar(8)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create index "IDX_TEMP_ELECTRICPIN_11"
    on WF_TEMP_ELECTRICPIN using ubtree ("PIID");

create index "IDX_TEMP_ELECTRICPIN_22"
    on WF_TEMP_ELECTRICPIN using ubtree ("TASKTARGETID");

create table WF_TEMP_LCRENEWID
(
    "POLICYNO"    varchar(30),
    "OLDCUSTID"   varchar(30),
    "NEWCUSTID"   varchar(60),
    "TARGETROWID" varchar(30),
    "DATATYPE"    varchar(1),
    "BRANCHNO"    varchar(100)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create index "IDX_TEMP_LCRENEWID_11"
    on WF_TEMP_LCRENEWID using ubtree ("POLICYNO");

create index "IDX_TEMP_LCRENEWID_22"
    on WF_TEMP_LCRENEWID using ubtree ("NEWCUSTID");

create table WF_TEMP_LCRENEWID_NOTIN
(
    "POLICYNO" varchar(30),
    "PIID"     varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TEMP_LCSL_WYSYGZ
(
    "ACTIVITYID"   varchar(30),
    "TASKTARGETID" varchar(30),
    "POLICYNO"     varchar(30),
    "OLDCUSTID"    varchar(30),
    "NEWCUSTID"    varchar(30),
    "TARGETROWID"  varchar(30),
    "DATATYPE"     varchar(1),
    "BRANCHNO"     varchar(100)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create index "IDX_TEMP_WYSYGZ_11"
    on WF_TEMP_LCSL_WYSYGZ using ubtree ("ACTIVITYID");

create index "IDX_TEMP_WYSYGZ_22"
    on WF_TEMP_LCSL_WYSYGZ using ubtree ("TASKTARGETID");

create table WF_TEMP_TASKRESERVATION1
(
    "RESERVATIONID"        varchar(30) not null,
    "APOINTMENTTIMESTART"  timestamp,
    "APOINTMENTTIMEEND"    timestamp,
    "APPOINTMENTREMARK"    varchar(1000),
    "APPOINTMENTADDRESS"   varchar(100),
    "COMID"                varchar(8),
    "NOTICETIME"           timestamp,
    "SMSFLAG"              varchar(10),
    "RESERVATIONSTATUS"    varchar(10),
    "INSERTTIMEFORHIS"     timestamp,
    "OPERATETIMEFORHIS"    timestamp,
    "UPDATERCODE"          varchar(20),
    "TASKID"               varchar(30),
    "SUCCESSFLAG"          varchar(10),
    "MOBILE"               varchar(30),
    "COMCODE"              varchar(8),
    "TASKCODE"             varchar(30),
    "PRIORITY"             varchar(3),
    "BPMPROCESSINSTANCEID" varchar(50)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TEMP_TODOTASK
(
    "TASKID" varchar(30),
    "PIID"   varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_ACTIVITYOBJECTINFO
(
    "ID_"           varchar(50) not null constraint "SYS_C0052956"
            primary key,
    "CUSTID_"       varchar(30) not null,
    "OBJECTID_"     varchar(30) not null,
    "SYSTEMFLAG_"   varchar(4),
    "COMCODE_"      varchar(20),
    "MONOPOLYCODE_" varchar(20),
    "COMID_"        varchar(20) not null,
    "CREATED_AT_"   timestamp   not null,
    "CREATED_BY_"   varchar(50) not null
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_TMP_ACTIVITYOBJECTINFO is '活动对象临时表。保存活动对象筛选SQL所产生的原始数据。';

comment on column WF_TMP_ACTIVITYOBJECTINFO."CUSTID_" is '活动对象对应的客户id';

comment on column WF_TMP_ACTIVITYOBJECTINFO."OBJECTID_" is '活动对象ID';

comment on column WF_TMP_ACTIVITYOBJECTINFO."SYSTEMFLAG_" is '对应营销系统中的SYSTEMFLAG';

comment on column WF_TMP_ACTIVITYOBJECTINFO."COMCODE_" is '活动对象归属的COMCODE（不一定是来自活动对象的属性，也可能是来自保单服务经理的属性）';

comment on column WF_TMP_ACTIVITYOBJECTINFO."MONOPOLYCODE_" is '车行代码';

comment on column WF_TMP_ACTIVITYOBJECTINFO."COMID_" is '归属省级分公司';

comment on column WF_TMP_ACTIVITYOBJECTINFO."CREATED_AT_" is '创建时间';

comment on column WF_TMP_ACTIVITYOBJECTINFO."CREATED_BY_" is '创建者（用户、筛选规则、外部数据源ID）';


create index "WF_TMP_ACTIVITYOBJECTINFO_1_"
    on WF_TMP_ACTIVITYOBJECTINFO using ubtree ("CUSTID_", "OBJECTID_");

create index "WF_TMP_ACTIVITYOBJECTINFO_2_"
    on WF_TMP_ACTIVITYOBJECTINFO using ubtree ("CUSTID_");

create index "WF_TMP_ACTIVITYOBJECTINFO_3_"
    on WF_TMP_ACTIVITYOBJECTINFO using ubtree ("OBJECTID_");

create index "WF_TMP_ACTIVITYOBJECTINFO_4_"
    on WF_TMP_ACTIVITYOBJECTINFO using ubtree ("COMCODE_");

create index "WF_TMP_ACTIVITYOBJECTINFO_5_"
    on WF_TMP_ACTIVITYOBJECTINFO using ubtree ("MONOPOLYCODE_");

create index "WF_TMP_ACTIVITYOBJECTINFO_6_"
    on WF_TMP_ACTIVITYOBJECTINFO using ubtree ("COMID_");

create table WF_TMP_CALLID
(
    "CALLID" varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_LCRENEWID
(
    "POLICYNO"    varchar(30),
    "OLDCUSTID"   varchar(30),
    "NEWCUSTID"   varchar(30),
    "TARGETROWID" varchar(30),
    "DATATYPE"    varchar(1),
    "BRANCHNO"    varchar(100)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create index "IDX_TMP_LCRENEWID_11"
    on WF_TMP_LCRENEWID using ubtree ("POLICYNO");

create index "IDX_TMP_LCRENEWID_22"
    on WF_TMP_LCRENEWID using ubtree ("NEWCUSTID");

create table WF_TMP_LCRENEWID_NOT
(
    "POLICYNO"    varchar(30),
    "CUSTID"      varchar(30),
    "PIID"        varchar(30),
    "VALIDSTATUS" varchar(10)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create index "IDX_TMP_LCRENEWID_NOT_11"
    on WF_TMP_LCRENEWID_NOT using ubtree ("POLICYNO");

create index "IDX_TMP_LCRENEWID_NOT__22"
    on WF_TMP_LCRENEWID_NOT using ubtree ("CUSTID");

create index "IDX_TMP_LCRENEWID_NOT__33"
    on WF_TMP_LCRENEWID_NOT using ubtree ("PIID");

create table WF_TMP_LCRENEWID_NOTIN
(
    "POLICYNO" varchar(30),
    "PIID"     varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_MANAGERTASKTURN
(
    "TASKID"      varchar(30),
    "MANAGERCODE" varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_MIDACTIVITYMESSAGE
(
    "JOINID"            varchar(50) not null,
    "STATUS"            varchar(5)  not null,
    "ASSIGNTYPE"        varchar(3)  not null,
    "ACTIVITYID"        varchar(30) not null,
    "TARGETTYPE"        varchar(30),
    "TARGETID"          varchar(30) not null,
    "CUSTID"            varchar(30) not null,
    "COMID"             varchar(8)  not null,
    "COMCODE"           varchar(8)  not null,
    "CREATECODE"        varchar(30),
    "OPERATORCODE"      varchar(30) not null,
    "SYSTEMFLAG"        varchar(12) not null,
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "LOADTIME"          timestamp,
    "UPDATECODE"        varchar(30),
    "DATASOURCE"        varchar(50),
    "BATCHNO"           varchar(50),
    "REMARK"            varchar(255)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_POLICYDETAIL_REPORT
(
    "POLICYNO"          varchar(22) not null,
    "CARID"             varchar(30),
    "CUSTID"            varchar(30),
    "KHSTCUSTID"        varchar(30),
    "POLICYOPERATOR"    varchar(300),
    "COMID"             varchar(8),
    "COMCODE"           varchar(8),
    "USERTYPE"          varchar(2),
    "CUSTSTATUSTYPE"    varchar(2),
    "PREMIUM"           numeric(14, 2),
    "VALIDTIME"         timestamp,
    "STARTDATE"         timestamp,
    "ENDDATE"           timestamp,
    "RISKCODE"          char(3),
    "PIID"              varchar(30),
    "TASKID"            varchar(30),
    "PROCESSID"         varchar(30),
    "ACTIVITYID"        varchar(30),
    "NEWMANAGERCODE"    varchar(360),
    "ISFAMILYCAR"       varchar(2),
    "CARSTATUS"         varchar(2),
    "COVERAGE"          varchar(2),
    "UPPERPATH"         varchar(300),
    "MONOPOLYCODE"      varchar(33),
    "VALIDSTATUS"       varchar(2),
    "TRANS_TYPE"        varchar(2),
    "TP_INPUTTIME"      timestamp,
    "DATASOURCE"        varchar(10),
    "LOADTIME"          timestamp,
    "OPERTYPE"          numeric(1000, 53),
    "LICENSENO"         varchar(30),
    "OPERATEDATE"       timestamp,
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "IS_JYC"            varchar(2),
    "RISKCODEFLAG"      varchar(5)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_TMP_POLICYDETAIL_REPORT is '上年成单人跑数临时表';

comment on column WF_TMP_POLICYDETAIL_REPORT."POLICYNO" is '保单号';

comment on column WF_TMP_POLICYDETAIL_REPORT."CARID" is '车辆ID';

comment on column WF_TMP_POLICYDETAIL_REPORT."CUSTID" is '客户ID';

comment on column WF_TMP_POLICYDETAIL_REPORT."KHSTCUSTID" is '客户视图ID';

comment on column WF_TMP_POLICYDETAIL_REPORT."POLICYOPERATOR" is '上年成单人';

comment on column WF_TMP_POLICYDETAIL_REPORT."COMID" is '8位机构号';

comment on column WF_TMP_POLICYDETAIL_REPORT."COMCODE" is '业务归属机构代码';

comment on column WF_TMP_POLICYDETAIL_REPORT."USERTYPE" is '用户类型';

comment on column WF_TMP_POLICYDETAIL_REPORT."CUSTSTATUSTYPE" is '客户类型';

comment on column WF_TMP_POLICYDETAIL_REPORT."PREMIUM" is '保费';

comment on column WF_TMP_POLICYDETAIL_REPORT."VALIDTIME" is '生效时间';

comment on column WF_TMP_POLICYDETAIL_REPORT."STARTDATE" is '起保时间';

comment on column WF_TMP_POLICYDETAIL_REPORT."ENDDATE" is '终保时间';

comment on column WF_TMP_POLICYDETAIL_REPORT."RISKCODE" is '险种代码';

comment on column WF_TMP_POLICYDETAIL_REPORT."PIID" is '流程实例ID';

comment on column WF_TMP_POLICYDETAIL_REPORT."TASKID" is '任务ID';

comment on column WF_TMP_POLICYDETAIL_REPORT."PROCESSID" is '流程ID';

comment on column WF_TMP_POLICYDETAIL_REPORT."ACTIVITYID" is '活动ID';

comment on column WF_TMP_POLICYDETAIL_REPORT."NEWMANAGERCODE" is '保单服务经理';

comment on column WF_TMP_POLICYDETAIL_REPORT."ISFAMILYCAR" is '是否家自车';

comment on column WF_TMP_POLICYDETAIL_REPORT."CARSTATUS" is '车辆类型';

comment on column WF_TMP_POLICYDETAIL_REPORT."COVERAGE" is '险种（1-车辆交强险，2-车辆商业险）';

comment on column WF_TMP_POLICYDETAIL_REPORT."UPPERPATH" is '上级机构列表';

comment on column WF_TMP_POLICYDETAIL_REPORT."MONOPOLYCODE" is '送修码';

comment on column WF_TMP_POLICYDETAIL_REPORT."VALIDSTATUS" is '是否有效';

comment on column WF_TMP_POLICYDETAIL_REPORT."TRANS_TYPE" is 'trans_type,成交类型 （1表示办理成交，2表示转投保成交）';

comment on column WF_TMP_POLICYDETAIL_REPORT."TP_INPUTTIME" is '保单的插入时间';

comment on column WF_TMP_POLICYDETAIL_REPORT."DATASOURCE" is '数据来源';

comment on column WF_TMP_POLICYDETAIL_REPORT."LOADTIME" is '装载时间';

comment on column WF_TMP_POLICYDETAIL_REPORT."OPERTYPE" is '操作类型';

comment on column WF_TMP_POLICYDETAIL_REPORT."LICENSENO" is '车牌号';

comment on column WF_TMP_POLICYDETAIL_REPORT."OPERATEDATE" is '签单日期';

comment on column WF_TMP_POLICYDETAIL_REPORT."INSERTTIMEFORHIS" is '插入时间';

comment on column WF_TMP_POLICYDETAIL_REPORT."OPERATETIMEFORHIS" is '更新时间';

comment on column WF_TMP_POLICYDETAIL_REPORT."IS_JYC" is '家用车标识,1,是，0，否';

comment on column WF_TMP_POLICYDETAIL_REPORT."RISKCODEFLAG" is '险种,1-商业险，2-交强险';


create table WF_TMP_PROADDBATCHNO
(
    "PIID"      varchar(100),
    "BATCHNO"   varchar(500),
    "BATCHNAME" varchar(500)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_PROCESSINSTANCEFINISH
(
    "PIID" varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_SCHDDX
(
    "PIID" varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_TASK
(
    "TASKID"               varchar(30),
    "TASKTARGETTYPE"       varchar(20),
    "TASKTARGETID"         varchar(30),
    "BPMPROCESSINSTANCEID" varchar(50),
    "ACTIVITYNAME"         varchar(50),
    "NODENAME"             varchar(50),
    "NODENO"               numeric(1000, 53),
    "TASKSTARTTIME"        timestamp,
    "TASKENDTIME"          timestamp,
    "NODEID"               varchar(30),
    "CUSTID"               varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_TASK_11
(
    "ACTIVITYID"           varchar(30),
    "NODEID"               varchar(30),
    "BPMPROCESSINSTANCEID" varchar(50)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_TASK_22
(
    "ACTIVITYID"           varchar(30),
    "NODEID"               varchar(30),
    "BPMPROCESSINSTANCEID" varchar(50)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_TASKHISTORY
(
    "TASKID" varchar(30),
    "PIID"   varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_TASKSHAREPOOL
(
    "TASKID" varchar(30) not null
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_TMP_TASKSHAREPOOL is '待认领任务临时表';

comment on column WF_TMP_TASKSHAREPOOL."TASKID" is 'taskId,任务ID';


create index "WF_TMP_SHARETASKIDINDEX"
    on WF_TMP_TASKSHAREPOOL using ubtree ("TASKID");

create table WF_TMP_TASKTARGET
(
    "TASKID"               varchar(30),
    "TASKTARGETTYPE"       varchar(20),
    "TASKTARGETID"         varchar(30),
    "BPMPROCESSINSTANCEID" varchar(50),
    "ACTIVITYNAME"         varchar(50),
    "NODENAME"             varchar(50),
    "NODENO"               numeric(1000, 53),
    "TASKSTARTTIME"        timestamp,
    "TASKENDTIME"          timestamp,
    "NODEID"               varchar(30),
    "TRADESTATUSREASON"    varchar(20),
    "CUSTID"               varchar(30),
    "TRACKTRADESTATUS"     varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_USERMESSAGE
(
    "MESSAGEID"            varchar(30) not null constraint "PK_WF_TMP_USERMESSAGE"
            primary key,
    "MESSAGENAME"          varchar(2000),
    "ACTIONURL"            varchar(500),
    "VALIDSTATUS"          varchar(1),
    "CREATORCODE"          varchar(10),
    "INSERTTIMEFORHIS"     timestamp,
    "UPDATERCODE"          varchar(10),
    "OPERATETIMEFORHIS"    timestamp,
    "COMID"                varchar(8)  not null,
    "RECEIVEDCODE"         varchar(10),
    "COMCODE"              varchar(8),
    "REMARK"               varchar(512),
    "MSGTYPE"              varchar(2),
    "ISREMIND"             varchar(2),
    "BPMPROCESSINSTANCEID" varchar(50)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_TMP_USERMESSAGE is '用户消息临时表';

comment on column WF_TMP_USERMESSAGE."MESSAGEID" is 'MessageId,消息ID';

comment on column WF_TMP_USERMESSAGE."MESSAGENAME" is 'MessageName,消息名';

comment on column WF_TMP_USERMESSAGE."ACTIONURL" is 'ActionURL,消息URL';

comment on column WF_TMP_USERMESSAGE."VALIDSTATUS" is 'ValidStatus,读取状态';

comment on column WF_TMP_USERMESSAGE."CREATORCODE" is 'CreatorCode,创建人代码';

comment on column WF_TMP_USERMESSAGE."INSERTTIMEFORHIS" is 'InsertTimeForHis,创建时间';

comment on column WF_TMP_USERMESSAGE."UPDATERCODE" is 'UpdaterCode,更新人代码';

comment on column WF_TMP_USERMESSAGE."OPERATETIMEFORHIS" is 'operateTimeForHis,更新时间';

comment on column WF_TMP_USERMESSAGE."COMID" is 'Comid,归属机构';

comment on column WF_TMP_USERMESSAGE."RECEIVEDCODE" is 'ReceivedCode,接收人代码';

comment on column WF_TMP_USERMESSAGE."COMCODE" is 'ComCode,归属机构代码';

comment on column WF_TMP_USERMESSAGE."REMARK" is 'Remark,备注';

comment on column WF_TMP_USERMESSAGE."MSGTYPE" is 'MsgType,用户消息类型：1—坐席登录状态，2—预约提醒，3—来电提醒，4—导入批次，5—免打扰审核，0或null—其他';

comment on column WF_TMP_USERMESSAGE."ISREMIND" is '0 未提醒  1 已提醒';


create table WF_TMP_USERMESSAGENOTREAD
(
    "MESSAGEID" varchar(50),
    "COMID"     varchar(50),
    "COMCODE"   varchar(50)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_TMP_USERTASKSUM
(
    "USERCODE"            varchar(30) not null,
    "TASKTODOSUM"         numeric(1000, 53),
    "TODAYTASKTODOSUM"    numeric(1000, 53),
    "CONTROLTASKSUM"      numeric(1000, 53),
    "CONTROLCALLTASKSUM"  numeric(1000, 53),
    "RESERVATIONTASKSUM"  numeric(1000, 53),
    "COMID"               varchar(8)  not null,
    "COMCODE"             varchar(8),
    "CREATORCODE"         varchar(30),
    "UPDATERCODE"         varchar(30),
    "INSERTTIMEFORHIS"    timestamp,
    "OPERATETIMEFORHIS"   timestamp,
    "BIRTHDAYRESERVATION" numeric(1000, 53),
    constraint "PK_WF_TMP_USERTASKSUM"
        primary key ("USERCODE", "COMID")
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on column WF_TMP_USERTASKSUM."BIRTHDAYRESERVATION" is '生日预约锁定数量';


create table WF_T_ABANDONEDTASK
(
    "ATID"              varchar(30) not null constraint "PK_WF_T_ABANDONEDTASK1"
            primary key,
    "TASKTARGETID"      varchar(30),
    "TASKTARGETTYPE"    varchar(20),
    "OLDACTIVITYID"     varchar(30),
    "OLDOPERATORCODE"   varchar(30),
    "COMID"             varchar(8)  not null,
    "COMCODE"           varchar(8),
    "INSERTTIMEFORHIS"  timestamp   not null,
    "REMARK"            varchar(100),
    "OPERATETIMEFORHIS" timestamp
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ABANDONEDTASK is 'WF_T_ABANDONEDTASK, 保护期内放弃任务';

comment on column WF_T_ABANDONEDTASK."ATID" is 'atid,主键ID';

comment on column WF_T_ABANDONEDTASK."TASKTARGETID" is 'tasktargetid,任务对象ID';

comment on column WF_T_ABANDONEDTASK."TASKTARGETTYPE" is 'tasktargettype,任务对象类型';

comment on column WF_T_ABANDONEDTASK."OLDACTIVITYID" is 'oldactivityid,活动ID';

comment on column WF_T_ABANDONEDTASK."OLDOPERATORCODE" is 'oldoperatorcode,任务操作人';

comment on column WF_T_ABANDONEDTASK."COMID" is 'comid,省级机构ID';

comment on column WF_T_ABANDONEDTASK."COMCODE" is 'comcode,归属机构代码';

comment on column WF_T_ABANDONEDTASK."INSERTTIMEFORHIS" is 'inserttimeforhis,插入时间';

comment on column WF_T_ABANDONEDTASK."REMARK" is 'remark,备注';

comment on column WF_T_ABANDONEDTASK."OPERATETIMEFORHIS" is 'operatetimeforhis,更新时间';


create index "IDX_ABANDONED_INSERTTIME"
    on WF_T_ABANDONEDTASK using ubtree ("INSERTTIMEFORHIS");

create table WF_T_ABANDONEDTASKVERIFY
(
    "ATVID"                varchar(30) not null,
    "TASKID"               varchar(30),
    "BPMPROCESSINSTANCEID" varchar(30),
    "TASKTARGETID"         varchar(30),
    "TASKTARGETTYPE"       varchar(20),
    "ACTIVITYID"           varchar(30),
    "OPERATORCODE"         varchar(30),
    "UPDATERCODE"          varchar(30),
    "COMID"                varchar(8)  not null,
    "COMCODE"              varchar(8),
    "INSERTTIMEFORHIS"     timestamp,
    "OPERATETIMEFORHIS"    timestamp,
    "VERIFYSTATUS"         varchar(2)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);


create table WF_T_ABNORMALONLINEUSER
(
    "ID"                varchar(30) not null constraint "PK_WF_T_ABNORMALONLINEUSER"
            primary key,
    "COMID"             varchar(8)  not null,
    "COMCODE"           varchar(8),
    "COMNAME"           varchar(300),
    "TEAMCODE"          varchar(10),
    "TEAMNAME"          varchar(300),
    "USERCODE"          varchar(50) not null,
    "USERNAME"          varchar(300),
    "CONTOFFLINEDAYS"   varchar(12),
    "LEAVETYPENAME"     varchar(300),
    "WORKDAYSRJTS"      numeric(20, 2),
    "TEAMUSERLEAVEFLAG" varchar(2),
    "REGISTRATIONTIME"  timestamp,
    "YEARMONTH"         varchar(10) not null,
    "ABNORMALFLAG"      varchar(2),
    "REASONDESC"        varchar(1000),
    "LASTOPERATECODE"   varchar(50),
    "LASTOPERATENAME"   varchar(300),
    "INSERTTIMEFORHIS"  timestamp   not null,
    "OPERATETIMEFORHIS" timestamp
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ABNORMALONLINEUSER is '异常上线坐席清单表';

comment on column WF_T_ABNORMALONLINEUSER."ID" is '自增主键';

comment on column WF_T_ABNORMALONLINEUSER."COMID" is 'COMID';

comment on column WF_T_ABNORMALONLINEUSER."COMCODE" is '机构代码';

comment on column WF_T_ABNORMALONLINEUSER."COMNAME" is '机构名称';

comment on column WF_T_ABNORMALONLINEUSER."TEAMCODE" is '团队代码';

comment on column WF_T_ABNORMALONLINEUSER."TEAMNAME" is '团队名称';

comment on column WF_T_ABNORMALONLINEUSER."USERCODE" is '坐席代码';

comment on column WF_T_ABNORMALONLINEUSER."USERNAME" is '坐席名称';

comment on column WF_T_ABNORMALONLINEUSER."CONTOFFLINEDAYS" is '近两个月内连续未上线天数';

comment on column WF_T_ABNORMALONLINEUSER."LEAVETYPENAME" is '请假类型中文名称';

comment on column WF_T_ABNORMALONLINEUSER."WORKDAYSRJTS" is '近一个月工作日日均通时';

comment on column WF_T_ABNORMALONLINEUSER."TEAMUSERLEAVEFLAG" is '是否计划离职坐席，0-否，1-计划离职坐席';

comment on column WF_T_ABNORMALONLINEUSER."REGISTRATIONTIME" is '坐席注册时间（上线人员清单-入司时间）';

comment on column WF_T_ABNORMALONLINEUSER."YEARMONTH" is '统计年月，格式为yyyy-mm';

comment on column WF_T_ABNORMALONLINEUSER."ABNORMALFLAG" is '是否异常，1-是，0-否';

comment on column WF_T_ABNORMALONLINEUSER."REASONDESC" is '原因说明';

comment on column WF_T_ABNORMALONLINEUSER."LASTOPERATECODE" is '最近操作人代码';

comment on column WF_T_ABNORMALONLINEUSER."LASTOPERATENAME" is '最近操作人名称';

comment on column WF_T_ABNORMALONLINEUSER."INSERTTIMEFORHIS" is '创建时间';

comment on column WF_T_ABNORMALONLINEUSER."OPERATETIMEFORHIS" is '修改时间';


create index "IDX_TEAMCODE_YEARMONTH"
    on WF_T_ABNORMALONLINEUSER using ubtree ("TEAMCODE", "YEARMONTH");

create table WF_T_ACRMCUSTOMERPORTRAITLOG
(
    "ACRMLOGID"         varchar(30) not null constraint "PK_ACRMCUSTOMERPORTRAITLOG"
            primary key,
    "TASKID"            varchar(30),
    "PIID"              varchar(30),
    "CUSTID"            varchar(30),
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "COMID"             varchar(8)  not null,
    "USERCODE"          varchar(30),
    "CREATORCODE"       varchar(30),
    "UPDATERCODE"       varchar(30),
    "USERNAME"          varchar(300)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACRMCUSTOMERPORTRAITLOG is 'ACRM客户画像记录日志';

comment on column WF_T_ACRMCUSTOMERPORTRAITLOG."ACRMLOGID" is 'ACRM客户画像记录日志id';

comment on column WF_T_ACRMCUSTOMERPORTRAITLOG."TASKID" is 'ACRM客户画像记录日志id';

comment on column WF_T_ACRMCUSTOMERPORTRAITLOG."PIID" is 'ACRM客户画像记录日志id';

comment on column WF_T_ACRMCUSTOMERPORTRAITLOG."CUSTID" is 'ACRM客户画像记录日志id';

comment on column WF_T_ACRMCUSTOMERPORTRAITLOG."INSERTTIMEFORHIS" is '创建时间';

comment on column WF_T_ACRMCUSTOMERPORTRAITLOG."OPERATETIMEFORHIS" is '更新时间';

comment on column WF_T_ACRMCUSTOMERPORTRAITLOG."COMID" is 'ComId,8位机构号';

comment on column WF_T_ACRMCUSTOMERPORTRAITLOG."USERCODE" is 'usercode,用户编码';

comment on column WF_T_ACRMCUSTOMERPORTRAITLOG."CREATORCODE" is 'creatorcode,创建人编码';

comment on column WF_T_ACRMCUSTOMERPORTRAITLOG."UPDATERCODE" is 'updatercode,更新人编码';

comment on column WF_T_ACRMCUSTOMERPORTRAITLOG."USERNAME" is 'username,用户名称';


create table WF_T_ACRMENQZTASK
(
    "TASKID"           varchar(40) not null constraint "SYS_C0054126"
            primary key,
    "TASKNAME"         varchar(200),
    "COMID"            varchar(20) not null,
    "BELONGERCODE"     varchar(20),
    "BELONGERCODETYPE" varchar(20),
    "BELONGERUSERCODE" varchar(20),
    "TARGETID"         varchar(66),
    "TARGETCUSTID"     varchar(40),
    "STATUS"           varchar(4),
    "VALIDSTATUS"      varchar(2),
    "INSERTTIMEFORHIS" timestamp,
    "CREATORCODE"      varchar(20),
    "UPDATETIMEFORHIS" timestamp,
    "UPDATECODE"       varchar(20)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACRMENQZTASK is 'WF_T_ACRMENQZTASK ACRM潜在法人企业任务表';

comment on column WF_T_ACRMENQZTASK."TASKID" is '主键';

comment on column WF_T_ACRMENQZTASK."TASKNAME" is '任务名称';

comment on column WF_T_ACRMENQZTASK."COMID" is '省级机构id';

comment on column WF_T_ACRMENQZTASK."BELONGERCODE" is '省级机构代码';

comment on column WF_T_ACRMENQZTASK."BELONGERCODETYPE" is '归属机构类型';

comment on column WF_T_ACRMENQZTASK."BELONGERUSERCODE" is '归属用户代码';

comment on column WF_T_ACRMENQZTASK."TARGETID" is '对象Id';

comment on column WF_T_ACRMENQZTASK."TARGETCUSTID" is '对象客户Id';

comment on column WF_T_ACRMENQZTASK."STATUS" is '任务状态';

comment on column WF_T_ACRMENQZTASK."VALIDSTATUS" is '是否有效';

comment on column WF_T_ACRMENQZTASK."INSERTTIMEFORHIS" is '插入时间';

comment on column WF_T_ACRMENQZTASK."CREATORCODE" is '创建人';

comment on column WF_T_ACRMENQZTASK."UPDATETIMEFORHIS" is '更新时间';

comment on column WF_T_ACRMENQZTASK."UPDATECODE" is '更新人';


create index "IDX_ENQZTASK_BCODE"
    on WF_T_ACRMENQZTASK using ubtree ("BELONGERCODE");

create index "IDX_ENQZTASK_BUSERCODE"
    on WF_T_ACRMENQZTASK using ubtree ("BELONGERUSERCODE");

create index "IDX_ENQZTASK_TARGETID"
    on WF_T_ACRMENQZTASK using ubtree ("TARGETID");

create index "IDX_ENQZTASK_TCUSTID"
    on WF_T_ACRMENQZTASK using ubtree ("TARGETCUSTID");

create table WF_T_ACRMENQZTASKALLOT
(
    "ALLOTID"           varchar(40) not null constraint "SYS_C0054131"
            primary key,
    "COMID"             varchar(10),
    "ALLOTTYPE"         varchar(2),
    "ALLOTCOUNT"        numeric(1000, 53),
    "ALLOTACTUALCOUNT"  numeric(1000, 53),
    "ALLOTSUCCEEDCOUNT" numeric(1000, 53),
    "ALLOTFAILCOUNT"    numeric(1000, 53),
    "ALLOTSTATE"        varchar(2),
    "ALLOTRESULTMSG"    varchar(4000),
    "ALLOTSTARTDATE"    timestamp,
    "ALLOTENDDATE"      timestamp,
    "OPERATIONCODE"     varchar(20),
    "VALIDSTATUS"       varchar(2),
    "INSERTTIMEFORHIS"  timestamp,
    "CREATORCODE"       varchar(20)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACRMENQZTASKALLOT is 'ACRM潜在法人企业任务表分配';

comment on column WF_T_ACRMENQZTASKALLOT."ALLOTID" is '主键';

comment on column WF_T_ACRMENQZTASKALLOT."COMID" is '省级机构id';

comment on column WF_T_ACRMENQZTASKALLOT."ALLOTTYPE" is '分配规则 1.按地市机构分配 2.手动指定分配';

comment on column WF_T_ACRMENQZTASKALLOT."ALLOTCOUNT" is '分配数(前端用户选择分配时显示的数)';

comment on column WF_T_ACRMENQZTASKALLOT."ALLOTACTUALCOUNT" is '分配实际数';

comment on column WF_T_ACRMENQZTASKALLOT."ALLOTSUCCEEDCOUNT" is '分配成功数';

comment on column WF_T_ACRMENQZTASKALLOT."ALLOTFAILCOUNT" is '分配失败数';

comment on column WF_T_ACRMENQZTASKALLOT."ALLOTSTATE" is '分配状态';

comment on column WF_T_ACRMENQZTASKALLOT."ALLOTRESULTMSG" is '分配结果内容';

comment on column WF_T_ACRMENQZTASKALLOT."ALLOTSTARTDATE" is '分配开始时间';

comment on column WF_T_ACRMENQZTASKALLOT."ALLOTENDDATE" is '分配结束时间';

comment on column WF_T_ACRMENQZTASKALLOT."OPERATIONCODE" is '分配操作人';

comment on column WF_T_ACRMENQZTASKALLOT."VALIDSTATUS" is '任务有效状态 1:有效 0:无效';

comment on column WF_T_ACRMENQZTASKALLOT."INSERTTIMEFORHIS" is '插入时间';

comment on column WF_T_ACRMENQZTASKALLOT."CREATORCODE" is '创建人';


create index "IDX_ALLOT_ALLOTSTATE"
    on WF_T_ACRMENQZTASKALLOT using ubtree ("ALLOTSTATE");

create index "IDX_ALLOT_INSERTTIMEFORHIS"
    on WF_T_ACRMENQZTASKALLOT using ubtree ("INSERTTIMEFORHIS");

create index "IDX_ALLOT_OPERATIONCODE"
    on WF_T_ACRMENQZTASKALLOT using ubtree ("OPERATIONCODE");

create table WF_T_ACRMENQZTASKALLOTTYPE2
(
    "ALLOTTYPEID"       varchar(40) not null constraint "SYS_C0054139"
            primary key,
    "COMID"             varchar(10),
    "ALLOTID"           varchar(40),
    "ALLOTCOMCODE"      varchar(20),
    "ALLOTTEAMUSERCODE" varchar(20),
    "ALLOTRATIO"        numeric(3),
    "VALIDSTATUS"       varchar(2),
    "INSERTTIMEFORHIS"  timestamp,
    "CREATORCODE"       varchar(20)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACRMENQZTASKALLOTTYPE2 is 'ACRM潜在法人企业任务表分配规则为2时记录表';

comment on column WF_T_ACRMENQZTASKALLOTTYPE2."ALLOTTYPEID" is '主键';

comment on column WF_T_ACRMENQZTASKALLOTTYPE2."COMID" is '省级机构id';

comment on column WF_T_ACRMENQZTASKALLOTTYPE2."ALLOTID" is '分配id';

comment on column WF_T_ACRMENQZTASKALLOTTYPE2."ALLOTCOMCODE" is '指定的机构/团队';

comment on column WF_T_ACRMENQZTASKALLOTTYPE2."ALLOTTEAMUSERCODE" is '指定的人';

comment on column WF_T_ACRMENQZTASKALLOTTYPE2."ALLOTRATIO" is '比率';

comment on column WF_T_ACRMENQZTASKALLOTTYPE2."VALIDSTATUS" is '任务有效状态 1:有效 0:无效';

comment on column WF_T_ACRMENQZTASKALLOTTYPE2."INSERTTIMEFORHIS" is '插入时间';

comment on column WF_T_ACRMENQZTASKALLOTTYPE2."CREATORCODE" is '创建人';


create index "IDX_ALLOTTYPE_ALLOTID"
    on WF_T_ACRMENQZTASKALLOTTYPE2 using ubtree ("ALLOTID");

create index "IDX_ALLOTTYPE_INSERTTIMEFORHIS"
    on WF_T_ACRMENQZTASKALLOTTYPE2 using ubtree ("INSERTTIMEFORHIS");

create table WF_T_ACRMENQZTASKTRACK
(
    "TRACKID"          varchar(40) not null constraint "SYS_C0054132"
            primary key,
    "COMID"            varchar(10),
    "TASKID"           varchar(40),
    "BELONGERCODE"     varchar(20),
    "BELONGERUSERCODE" varchar(20),
    "OPERATETYPE"      varchar(2),
    "OPERATECODE"      varchar(20),
    "VALIDSTATUS"      varchar(2),
    "INSERTTIMEFORHIS" timestamp,
    "CREATORCODE"      varchar(20)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACRMENQZTASKTRACK is 'ACRM潜在法人企业任务轨迹表';

comment on column WF_T_ACRMENQZTASKTRACK."TRACKID" is '主键';

comment on column WF_T_ACRMENQZTASKTRACK."COMID" is '省级机构id';

comment on column WF_T_ACRMENQZTASKTRACK."TASKID" is '任务id';

comment on column WF_T_ACRMENQZTASKTRACK."BELONGERCODE" is '归属的机构/团队';

comment on column WF_T_ACRMENQZTASKTRACK."BELONGERUSERCODE" is '归属的人';

comment on column WF_T_ACRMENQZTASKTRACK."OPERATETYPE" is '操作类型 1.分配 2.撤回 3.回退';

comment on column WF_T_ACRMENQZTASKTRACK."OPERATECODE" is '操作人';

comment on column WF_T_ACRMENQZTASKTRACK."VALIDSTATUS" is '任务有效状态 1:有效 0:无效';

comment on column WF_T_ACRMENQZTASKTRACK."INSERTTIMEFORHIS" is '插入时间';

comment on column WF_T_ACRMENQZTASKTRACK."CREATORCODE" is '创建人';


create index "IDX_ALLOTTRACK_BCODE"
    on WF_T_ACRMENQZTASKTRACK using ubtree ("BELONGERCODE");

create index "IDX_ALLOTTRACK_BUSERCODE"
    on WF_T_ACRMENQZTASKTRACK using ubtree ("BELONGERUSERCODE");

create index "IDX_ALLOTTRACK_OPERATECODE"
    on WF_T_ACRMENQZTASKTRACK using ubtree ("OPERATECODE");

create index "IDX_ALLOTTRACK_OPERATETYPE"
    on WF_T_ACRMENQZTASKTRACK using ubtree ("OPERATETYPE");

create index "IDX_ALLOTTRACK_TASKID"
    on WF_T_ACRMENQZTASKTRACK using ubtree ("TASKID");

create table WF_T_ACRMENTERPRISETASK
(
    "AETASKID"          varchar(40) not null constraint "SYS_C0054097"
            primary key,
    "AETASKNAME"        varchar(200),
    "COMID"             varchar(20) not null,
    "COMCODE"           varchar(20),
    "TARGETID"          varchar(66),
    "TARGETCUSTID"      varchar(40),
    "ENDDATE"           timestamp,
    "OPERATORCODE"      varchar(30),
    "STATUS"            varchar(4),
    "FINISHDATE"        timestamp,
    "VALIDSTATUS"       varchar(2),
    "INSERTTIMEFORHIS"  timestamp,
    "CREATORCODE"       varchar(20),
    "OPERATETIMEFORHIS" timestamp,
    "UPDATECODE"        varchar(20)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACRMENTERPRISETASK is 'acrmEnterpriseTask ACRM法人企业任务表';

comment on column WF_T_ACRMENTERPRISETASK."AETASKID" is 'aeTaskId主键';

comment on column WF_T_ACRMENTERPRISETASK."AETASKNAME" is 'aeTaskName任务名称';

comment on column WF_T_ACRMENTERPRISETASK."COMID" is 'comId省级机构代码';

comment on column WF_T_ACRMENTERPRISETASK."COMCODE" is 'comCode归属机构代码（存执行人的机构）';

comment on column WF_T_ACRMENTERPRISETASK."TARGETID" is 'targetId任务对象ID（面向MC_T_ENTERPRISEBASEINFO表）';

comment on column WF_T_ACRMENTERPRISETASK."TARGETCUSTID" is 'targetCustId任务对象客户ID（面向MC_T_ENTERPRISEBASEINFO表的custId）';

comment on column WF_T_ACRMENTERPRISETASK."OPERATORCODE" is 'operator,任务操作人';

comment on column WF_T_ACRMENTERPRISETASK."STATUS" is 'status任务状态 A.待分配 R.进行中（表示已分配） F.任务已完成';

comment on column WF_T_ACRMENTERPRISETASK."FINISHDATE" is 'finishDate任务完成时间';

comment on column WF_T_ACRMENTERPRISETASK."VALIDSTATUS" is 'validStatus任务有效状态 1:有效 0:无效';

comment on column WF_T_ACRMENTERPRISETASK."INSERTTIMEFORHIS" is 'inserttimeforhis插入时间';

comment on column WF_T_ACRMENTERPRISETASK."CREATORCODE" is 'creatorCode创建人';

comment on column WF_T_ACRMENTERPRISETASK."OPERATETIMEFORHIS" is 'operateTimeForHis插入时间';

comment on column WF_T_ACRMENTERPRISETASK."UPDATECODE" is 'operateCode更新人';


create index "IDX_AET_COMCODE"
    on WF_T_ACRMENTERPRISETASK using ubtree ("COMCODE");

create index "IDX_AET_OPERATORCODE"
    on WF_T_ACRMENTERPRISETASK using ubtree ("OPERATORCODE");

create index "IDX_AET_STATUS"
    on WF_T_ACRMENTERPRISETASK using ubtree ("STATUS");

create index "IDX_AET_TARGETID"
    on WF_T_ACRMENTERPRISETASK using ubtree ("TARGETID");

create table WF_T_ACTIVITY
(
    "ACTIVITYID"                 varchar(30) not null constraint "PK_WF_T_ACTIVITY"
            primary key,
    "ACTIVITYNAME"               varchar(200),
    "ACTIVITYTYPE"               varchar(12),
    "PROCESSID"                  varchar(30),
    "PRODPKGID"                  varchar(30),
    "ACTIVITYSTARTTIME"          timestamp,
    "ACTIVITYENDTIME"            timestamp,
    "RESOURCEPKGID"              varchar(20),
    "ACTIVITYFINISHSTATUS"       varchar(10),
    "ACTIVITYASSIGNSTATUS"       varchar(10),
    "COMID"                      varchar(8)  not null,
    "INSERTTIMEFORHIS"           timestamp,
    "OPERATETIMEFORHIS"          timestamp,
    "UPDATERCODE"                varchar(10),
    "COSTLIMIT"                  numeric(1000, 53),
    "PRICELIMIT"                 numeric(1000, 53),
    "SALETARGET"                 numeric(1000, 53),
    "TASKNUMBER"                 numeric(1000, 53),
    "REMARK"                     varchar(300),
    "ACTIVITYVALIDSTATUS"        varchar(1),
    "CREATORCODE"                varchar(10),
    "GROUPCODE"                  varchar(30),
    "TARGETTYPE"                 varchar(2),
    "CLOSESTATUS"                varchar(2),
    "COMCODE"                    varchar(8),
    "QUOTATIONNOTICE"            varchar(1),
    "ADDOBJSTATUS"               varchar(2),
    "FLAG"                       varchar(2),
    "LONGFLAG"                   varchar(2),
    "OCPHONEFLAG"                varchar(2),
    "ACTIVITYBUSINESSTYPE"       varchar(10),
    "ACTIVITYHQTYPE"             varchar(8),
    "INTELLIGENTCALLFLAG"        varchar(8),
    "ISCARMANAGER"               varchar(10),
    "ISCARADDACTIVITY"           varchar(10),
    "ISNEWMANAGERFLAG"           varchar(10),
    "INTELLIGENTDIALINGSCENE"    varchar(30),
    "ISBIRTHDAYTASKRESERVATION"  varchar(4),
    "ISCONTROLTRANSFERINSURANCE" varchar(2),
    "QUOTATIONCOMCODE"           varchar(30),
    "EDIANTONGFLAG"              varchar(10),
    "INTELLIGENCEOUTBOUND"       varchar(8),
    "CURRENTFLAG"                varchar(2),
    "TRACKERFLAG"                varchar(2),
    "NONCARSCENE"                varchar(4),
    "QUOTESOURCE"                varchar(2),
    "CUSTOMERSERVICETYPE"        varchar(2),
    "MODELRANK"                  varchar(2),
    "ISHIGHCONVERT"              varchar(2),
    "INTELLIGENTCALLYXFLAG"      varchar(8),
    "HOLIDAYCALLFLAG"            varchar(8),
    "TIMERANGE"                  varchar(100),
    "ISCST"                      varchar(2),
    "THREESIDEQUEUE"             varchar(2),
    "USERPOWERTEAM"              varchar(4),
    "TOPFLAG"                    varchar(2),
    "TOPFLAGUPDATETIME"          timestamp,
    "TOPFLAGPOWERCOMCODE"        varchar(8),
    "CIBITAG"                    varchar(2),
    "MOTORCARTAG"                varchar(2),
    "BEFORESTARTDATE"            numeric(1000, 53),
    "BEFOREENDDATE"              numeric(1000, 53),
    "RECALLTIME"                 numeric(1000, 53),
    "ADMINPERMISSIONS"           varchar(2),
    "ALLOWCHANGEENDDATEFLAG"     varchar(2),
    "USERCLASSIFICATIONCODE"     varchar(10),
    "DATARANGE"                  varchar(2),
    "USENATURECODE"              varchar(2),
    "NONNEXTCARBACKUP"           numeric(1000, 53),
    "NEXTCARBACKUP"              numeric(1000, 53),
    "EXCLUDEXT2"                 varchar(2),
    "ACTIVITYCHANNELTYPE"        varchar(2),
    "HOLIDAYTIMERANGE"           varchar(100),
    "INTELLIGENTLABELFIRST"      varchar(20),
    "INTELLIGENTLABELSECOND"     varchar(40),
    "TEAMSID"                    varchar(30),
    "FULLPROVIDE"                varchar(2)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACTIVITY is 'WF_T_Activity,活动信息表';

comment on column WF_T_ACTIVITY."ACTIVITYID" is 'ActivityID,活动ID';

comment on column WF_T_ACTIVITY."ACTIVITYNAME" is 'ActivityName,活动名称';

comment on column WF_T_ACTIVITY."ACTIVITYTYPE" is 'ActivityType,活动类型';

comment on column WF_T_ACTIVITY."PROCESSID" is 'ProcessID,流程ID';

comment on column WF_T_ACTIVITY."PRODPKGID" is 'ProdPkgID,产品方案ID';

comment on column WF_T_ACTIVITY."ACTIVITYSTARTTIME" is 'ActivityStartTime,活动开始时间';

comment on column WF_T_ACTIVITY."ACTIVITYENDTIME" is 'ActivityEndTime,活动结束时间';

comment on column WF_T_ACTIVITY."RESOURCEPKGID" is 'ResourcePkgID,资源包ID';

comment on column WF_T_ACTIVITY."ACTIVITYFINISHSTATUS" is 'ActivityFinishStatus,活动状态:已结束/未结束';

comment on column WF_T_ACTIVITY."ACTIVITYASSIGNSTATUS" is 'ActivityAssignStatus,已分配/未分配';

comment on column WF_T_ACTIVITY."COMID" is 'ComId,8位机构号';

comment on column WF_T_ACTIVITY."INSERTTIMEFORHIS" is 'InsertTimeForHis,插入时间';

comment on column WF_T_ACTIVITY."OPERATETIMEFORHIS" is 'OperateTimeForHis,更新时间';

comment on column WF_T_ACTIVITY."UPDATERCODE" is 'UpdaterCode,更新人';

comment on column WF_T_ACTIVITY."COSTLIMIT" is 'CostLimit,成本价限额';

comment on column WF_T_ACTIVITY."PRICELIMIT" is 'PriceLimit,市场价限额';

comment on column WF_T_ACTIVITY."SALETARGET" is 'SaleTarget,销售目标';

comment on column WF_T_ACTIVITY."TASKNUMBER" is 'TaskNumber,任务数量';

comment on column WF_T_ACTIVITY."REMARK" is 'Remark,活动描述';

comment on column WF_T_ACTIVITY."ACTIVITYVALIDSTATUS" is '有效性';

comment on column WF_T_ACTIVITY."CREATORCODE" is 'CreatorCode,创建人';

comment on column WF_T_ACTIVITY."GROUPCODE" is 'GroupCode,外部机构';

comment on column WF_T_ACTIVITY."TARGETTYPE" is 'TargetType,活动对象类型';

comment on column WF_T_ACTIVITY."CLOSESTATUS" is 'CloseStatus,活动是否关闭';

comment on column WF_T_ACTIVITY."COMCODE" is 'ComCode,归属机构代码';

comment on column WF_T_ACTIVITY."ADDOBJSTATUS" is 'AddObjStatus, 是否允许从客户视图添加活动对象。';

comment on column WF_T_ACTIVITY."FLAG" is 'flag活动类型标志，1表示续保团队活动 2表示综拓团队活动';

comment on column WF_T_ACTIVITY."LONGFLAG" is '是否长期有效标志位，1表示是，0表示否';

comment on column WF_T_ACTIVITY."OCPHONEFLAG" is '失联电话标志';

comment on column WF_T_ACTIVITY."ACTIVITYBUSINESSTYPE" is 'activityBusinessType,活动业务类型:substr(c.flag,3,1)=1用于已办加入活动查询';

comment on column WF_T_ACTIVITY."ACTIVITYHQTYPE" is 'activityHQType,总部活动分类标志位(1--续保业务类,2--转保业务类,3--客户服务类,4--非车险业务类,99--其他)';

comment on column WF_T_ACTIVITY."INTELLIGENTCALLFLAG" is '智能语音呼叫指定活动 1-是';

comment on column WF_T_ACTIVITY."ISCARMANAGER" is '划转更新车险管家(1-是 默认-不是)';

comment on column WF_T_ACTIVITY."ISCARADDACTIVITY" is '非车引流(1-是 默认-不是)';

comment on column WF_T_ACTIVITY."ISNEWMANAGERFLAG" is '同步更新保单服务经理(1-是 默认-不是)';

comment on column WF_T_ACTIVITY."INTELLIGENTDIALINGSCENE" is '智能语音拨打场景';

comment on column WF_T_ACTIVITY."ISBIRTHDAYTASKRESERVATION" is 'isBirthDayTaskReservation,是否有生日预约提醒 0或null为无 1为有';

comment on column WF_T_ACTIVITY."ISCONTROLTRANSFERINSURANCE" is '是否纳入续保强制拨打管控，1-纳入，其他-不纳入，需要配和systemConfig配置项（isShowControlTransferInsurance）开启';

comment on column WF_T_ACTIVITY."QUOTATIONCOMCODE" is '报价配置归属机构';

comment on column WF_T_ACTIVITY."EDIANTONGFLAG" is 'e点通活动标记';

comment on column WF_T_ACTIVITY."INTELLIGENCEOUTBOUND" is '网销家自车智能外呼活动 勾选后值是1，不勾选为空';

comment on column WF_T_ACTIVITY."CURRENTFLAG" is '当前标志位';

comment on column WF_T_ACTIVITY."TRACKERFLAG" is '任务同跟踪人划转：1代表开启';

comment on column WF_T_ACTIVITY."NONCARSCENE" is '非车场景';

comment on column WF_T_ACTIVITY."QUOTESOURCE" is '报价类型（1-报价/0-未报价）';

comment on column WF_T_ACTIVITY."CUSTOMERSERVICETYPE" is '客户类型（1-新转保/2-续保/0-不确定）';

comment on column WF_T_ACTIVITY."MODELRANK" is '模型评分选项（1-高/0-低）';

comment on column WF_T_ACTIVITY."ISHIGHCONVERT" is '是否高转化（1-是/0-否）';

comment on column WF_T_ACTIVITY."INTELLIGENTCALLYXFLAG" is '智能营销语音外呼标志 1-是';

comment on column WF_T_ACTIVITY."HOLIDAYCALLFLAG" is '节假日外呼标志 1-是  其他-否';

comment on column WF_T_ACTIVITY."TIMERANGE" is '发送时间段';

comment on column WF_T_ACTIVITY."ISCST" is '车商通活动标识（1-是车商通活动 为空-非车商通活动）';

comment on column WF_T_ACTIVITY."THREESIDEQUEUE" is '1-三方合作续保队列 2-三方合作暂存队列';

comment on column WF_T_ACTIVITY."USERPOWERTEAM" is 'userPowerTeam, 用户团队类型 16:续保团队二  99||空:分公司及其他';

comment on column WF_T_ACTIVITY."TOPFLAG" is '置顶标志位';

comment on column WF_T_ACTIVITY."TOPFLAGUPDATETIME" is '置顶标志位更新时间';

comment on column WF_T_ACTIVITY."TOPFLAGPOWERCOMCODE" is '置顶标志位权限comCode';

comment on column WF_T_ACTIVITY."CIBITAG" is '混合投保单标志 1-单交强投保单、2-单商业投保单、3-混保投保单';

comment on column WF_T_ACTIVITY."MOTORCARTAG" is '机动车标志 1-摩托车投保单、2-家自车投保单单';

comment on column WF_T_ACTIVITY."BEFORESTARTDATE" is '推送提前起始天数';

comment on column WF_T_ACTIVITY."BEFOREENDDATE" is '推送提前截止天数';

comment on column WF_T_ACTIVITY."RECALLTIME" is '重呼时间间隔(分钟)';

comment on column WF_T_ACTIVITY."ADMINPERMISSIONS" is 'admin管理员操作权限(1-是/0-否)';

comment on column WF_T_ACTIVITY."ALLOWCHANGEENDDATEFLAG" is '是否允许修改车辆终保日期标志';

comment on column WF_T_ACTIVITY."USERCLASSIFICATIONCODE" is '团队分类代码';

comment on column WF_T_ACTIVITY."DATARANGE" is '数据范围 01-续保库、02-脱保库、03-回访库、99-其他';

comment on column WF_T_ACTIVITY."USENATURECODE" is '车辆使用性质 1-家用车、2-非营业客车、3-非营业货车、4-其他';

comment on column WF_T_ACTIVITY."NONNEXTCARBACKUP" is '非次新车上限兜底值兜底值';

comment on column WF_T_ACTIVITY."NEXTCARBACKUP" is '次新车上限兜底值兜底值';

comment on column WF_T_ACTIVITY."EXCLUDEXT2" is '剔除上年服务经理为续团2的业务 1-是, 0/空-否';

comment on column WF_T_ACTIVITY."ACTIVITYCHANNELTYPE" is '活动渠道 1.蚂蚁';

comment on column WF_T_ACTIVITY."HOLIDAYTIMERANGE" is '节假日发送时间段';

comment on column WF_T_ACTIVITY."INTELLIGENTLABELFIRST" is '标签大类';

comment on column WF_T_ACTIVITY."INTELLIGENTLABELSECOND" is '标签小类';

comment on column WF_T_ACTIVITY."TEAMSID" is '团队集合ID';

comment on column WF_T_ACTIVITY."FULLPROVIDE" is '是否全量兜底';


create index "PROCESSIDINDEX"
    on WF_T_ACTIVITY using ubtree ("PROCESSID");

create table WF_T_ACTIVITY_ERR
(
    "ACTIVITYID"                 varchar(30) not null constraint "PK_WF_T_ACTIVITY_ERR"
            primary key,
    "ACTIVITYNAME"               varchar(200),
    "ACTIVITYTYPE"               varchar(12),
    "PROCESSID"                  varchar(30),
    "PRODPKGID"                  varchar(30),
    "ACTIVITYSTARTTIME"          timestamp,
    "ACTIVITYENDTIME"            timestamp,
    "RESOURCEPKGID"              varchar(20),
    "ACTIVITYFINISHSTATUS"       varchar(10),
    "ACTIVITYASSIGNSTATUS"       varchar(10),
    "COMID"                      varchar(8)  not null,
    "INSERTTIMEFORHIS"           timestamp,
    "OPERATETIMEFORHIS"          timestamp,
    "UPDATERCODE"                varchar(10),
    "COSTLIMIT"                  numeric(1000, 53),
    "PRICELIMIT"                 numeric(1000, 53),
    "SALETARGET"                 numeric(1000, 53),
    "TASKNUMBER"                 numeric(1000, 53),
    "REMARK"                     varchar(300),
    "ACTIVITYVALIDSTATUS"        varchar(2),
    "CREATORCODE"                varchar(10),
    "GROUPCODE"                  varchar(30),
    "TARGETTYPE"                 varchar(2),
    "CLOSESTATUS"                varchar(2),
    "COMCODE"                    varchar(8),
    "QUOTATIONNOTICE"            varchar(2),
    "ADDOBJSTATUS"               varchar(2),
    "FLAG"                       varchar(2),
    "LONGFLAG"                   varchar(2),
    "OCPHONEFLAG"                varchar(2),
    "ACTIVITYBUSINESSTYPE"       varchar(10),
    "ACTIVITYHQTYPE"             varchar(8),
    "INTELLIGENTCALLFLAG"        varchar(8),
    "ISCARMANAGER"               varchar(10),
    "ISCARADDACTIVITY"           varchar(10),
    "ISNEWMANAGERFLAG"           varchar(10),
    "INTELLIGENTDIALINGSCENE"    varchar(30),
    "ISCONTROLTRANSFERINSURANCE" varchar(2)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACTIVITY_ERR is 'WF_T_ACTIVITY_ERR,活动信息表';

comment on column WF_T_ACTIVITY_ERR."ACTIVITYID" is 'ActivityID,活动ID';

comment on column WF_T_ACTIVITY_ERR."ACTIVITYNAME" is 'ActivityName,活动名称';

comment on column WF_T_ACTIVITY_ERR."ACTIVITYTYPE" is 'ActivityType,活动类型<1,1-营销类;1,营销类;2,销售类;3,服务类;>';

comment on column WF_T_ACTIVITY_ERR."PROCESSID" is 'ProcessID,流程ID';

comment on column WF_T_ACTIVITY_ERR."PRODPKGID" is 'ProdPkgID,产品方案ID';

comment on column WF_T_ACTIVITY_ERR."ACTIVITYSTARTTIME" is 'ActivityStartTime,活动开始时间';

comment on column WF_T_ACTIVITY_ERR."ACTIVITYENDTIME" is 'ActivityEndTime,活动结束时间';

comment on column WF_T_ACTIVITY_ERR."RESOURCEPKGID" is 'ResourcePkgID,资源包ID';

comment on column WF_T_ACTIVITY_ERR."ACTIVITYFINISHSTATUS" is 'ActivityFinishStatus,活动状态:已结束/未结束<1,未完成;2,已完成;>';

comment on column WF_T_ACTIVITY_ERR."ACTIVITYASSIGNSTATUS" is 'ActivityAssignStatus,已分配/未分配';

comment on column WF_T_ACTIVITY_ERR."COMID" is 'ComId,8位机构号';

comment on column WF_T_ACTIVITY_ERR."INSERTTIMEFORHIS" is 'InsertTimeForHis,插入时间';

comment on column WF_T_ACTIVITY_ERR."OPERATETIMEFORHIS" is 'OperateTimeForHis,更新时间';

comment on column WF_T_ACTIVITY_ERR."UPDATERCODE" is 'UpdaterCode,更新人';

comment on column WF_T_ACTIVITY_ERR."COSTLIMIT" is 'CostLimit,成本价限额';

comment on column WF_T_ACTIVITY_ERR."PRICELIMIT" is 'PriceLimit,市场价限额';

comment on column WF_T_ACTIVITY_ERR."SALETARGET" is 'SaleTarget,销售目标';

comment on column WF_T_ACTIVITY_ERR."TASKNUMBER" is 'TaskNumber,任务数量';

comment on column WF_T_ACTIVITY_ERR."REMARK" is 'Remark,活动描述';

comment on column WF_T_ACTIVITY_ERR."ACTIVITYVALIDSTATUS" is '有效状态';

comment on column WF_T_ACTIVITY_ERR."CREATORCODE" is 'CreatorCode,创建人';

comment on column WF_T_ACTIVITY_ERR."GROUPCODE" is 'GroupCode,外部机构';

comment on column WF_T_ACTIVITY_ERR."TARGETTYPE" is 'TargetType,活动对象类型';

comment on column WF_T_ACTIVITY_ERR."CLOSESTATUS" is 'CloseStatus,活动是否关闭<1,未关闭;2,已关闭;>';

comment on column WF_T_ACTIVITY_ERR."COMCODE" is 'ComCode,归属机构代码';

comment on column WF_T_ACTIVITY_ERR."QUOTATIONNOTICE" is '承保通知标志位';

comment on column WF_T_ACTIVITY_ERR."ADDOBJSTATUS" is 'AddObjStatus, 是否允许从客户视图添加活动对象。';

comment on column WF_T_ACTIVITY_ERR."FLAG" is 'flag用作活动的标志位，1表示续保活动';

comment on column WF_T_ACTIVITY_ERR."LONGFLAG" is '是否长期有效标志位，1表示是，0表示否';

comment on column WF_T_ACTIVITY_ERR."OCPHONEFLAG" is 'OCPHONEFLAG,失联电话标志';

comment on column WF_T_ACTIVITY_ERR."ACTIVITYBUSINESSTYPE" is 'activityBusinessType,活动业务类型:substr(c.flag,3,1)=1用于已办加入活动查询';

comment on column WF_T_ACTIVITY_ERR."ACTIVITYHQTYPE" is 'activityHQType,总部活动分类标志位(1--续保业务类,2--转保业务类,3--客户服务类,4--非车险业务类,99--其他)';

comment on column WF_T_ACTIVITY_ERR."INTELLIGENTCALLFLAG" is '智能语音呼叫指定活动 1-是';

comment on column WF_T_ACTIVITY_ERR."ISCARMANAGER" is '划转更新车险管家(1-是 默认-不是)';

comment on column WF_T_ACTIVITY_ERR."ISCARADDACTIVITY" is '非车引流(1-是 默认-不是)';

comment on column WF_T_ACTIVITY_ERR."ISNEWMANAGERFLAG" is '同步更新保单服务经理(1-是 默认-不是)';

comment on column WF_T_ACTIVITY_ERR."INTELLIGENTDIALINGSCENE" is '智能语音拨打场景';

comment on column WF_T_ACTIVITY_ERR."ISCONTROLTRANSFERINSURANCE" is '是否纳入续保强制拨打管控，1-纳入，其他-不纳入，需要配和systemConfig配置项（isShowControlTransferInsurance）开启';


create index "IDX_ACTIVITY_PROCESSID11"
    on WF_T_ACTIVITY_ERR using ubtree ("PROCESSID");

create table WF_T_ACTIVITYOBJECTFILTER
(
    "FILTERID"           varchar(30) not null constraint "PK_WF_T_ACTIVITYOBJECTFILTER"
            primary key,
    "FILTERNAME"         varchar(200),
    "REMARK"             varchar(1000),
    "SQL"                varchar(4000),
    "ACTIVITYTARGETTYPE" varchar(1),
    "RESOURCETYPE"       varchar(1),
    "COMID"              varchar(8),
    "COMCODE"            varchar(8),
    "CREATORCODE"        varchar(30),
    "UPDATERCODE"        varchar(30),
    "INSERTTIMEFORHIS"   timestamp,
    "OPERATETIMEFORHIS"  timestamp,
    "SQLADDITION"        varchar(4000),
    "SCENARIOJSONSTRING" varchar(4000),
    "SCENARIO"           varchar(30),
    "INCREATETYPE"       varchar(2),
    "ADGFLAG"            varchar(2),
    "INCREATESQL"        varchar(4000)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on column WF_T_ACTIVITYOBJECTFILTER."FILTERID" is 'filterId,规则ID';

comment on column WF_T_ACTIVITYOBJECTFILTER."FILTERNAME" is 'filterName,规则名称';

comment on column WF_T_ACTIVITYOBJECTFILTER."REMARK" is 'remark,详细说明';

comment on column WF_T_ACTIVITYOBJECTFILTER."SQL" is 'sql,语句';

comment on column WF_T_ACTIVITYOBJECTFILTER."ACTIVITYTARGETTYPE" is 'activityTargetType,对象类型';

comment on column WF_T_ACTIVITYOBJECTFILTER."RESOURCETYPE" is 'resourceType,对象来源';

comment on column WF_T_ACTIVITYOBJECTFILTER."COMID" is 'comId,机构代码';

comment on column WF_T_ACTIVITYOBJECTFILTER."COMCODE" is 'comCode,业务代码';

comment on column WF_T_ACTIVITYOBJECTFILTER."CREATORCODE" is 'creatorCode,创建人';

comment on column WF_T_ACTIVITYOBJECTFILTER."UPDATERCODE" is 'updaterCode,更新人';

comment on column WF_T_ACTIVITYOBJECTFILTER."INSERTTIMEFORHIS" is 'insertTimeForHis,插入时间';

comment on column WF_T_ACTIVITYOBJECTFILTER."OPERATETIMEFORHIS" is 'operateTimeForHis,更新时间';

comment on column WF_T_ACTIVITYOBJECTFILTER."SCENARIOJSONSTRING" is 'SCENARIOJSONSTRING,场景配置JSON';

comment on column WF_T_ACTIVITYOBJECTFILTER."SCENARIO" is 'SCENARIO,场景';

comment on column WF_T_ACTIVITYOBJECTFILTER."INCREATETYPE" is 'INCREATETYPE,增量模式';

comment on column WF_T_ACTIVITYOBJECTFILTER."ADGFLAG" is 'adg跑数标志：1-使用adg';

comment on column WF_T_ACTIVITYOBJECTFILTER."INCREATESQL" is '增量sql，increateType为3时该字段有值';


create table WF_T_ACTIVITYOBJECTINFO
(
    "ID_"           varchar(50) not null,
    "BATCHID_"      varchar(50) not null,
    "CUSTID_"       varchar(30) not null,
    "OBJECTID_"     varchar(30) not null,
    "SYSTEMFLAG_"   varchar(4),
    "COMCODE_"      varchar(20),
    "MONOPOLYCODE_" varchar(40),
    "STATE_"        numeric(4)  not null,
    "CREATED_AT_"   timestamp   not null,
    "CREATED_BY_"   varchar(50) not null,
    "VERIFIED_AT_"  timestamp,
    "COMID_"        varchar(20) not null,
    "STATUS_"       varchar(4)  not null,
    "REMARK_"       text
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACTIVITYOBJECTINFO is '活动对象正式表，保存经过处理的数据。例如经过数据权限筛选。';

comment on column WF_T_ACTIVITYOBJECTINFO."BATCHID_" is '批次号';

comment on column WF_T_ACTIVITYOBJECTINFO."CUSTID_" is '活动对象对应的客户id';

comment on column WF_T_ACTIVITYOBJECTINFO."OBJECTID_" is '活动对象ID';

comment on column WF_T_ACTIVITYOBJECTINFO."SYSTEMFLAG_" is '对应营销系统中的SYSTEMFLAG';

comment on column WF_T_ACTIVITYOBJECTINFO."COMCODE_" is '活动对象归属的COMCODE（不一定是来自活动对象的属性，也可能是来自保单服务经理的属性）';

comment on column WF_T_ACTIVITYOBJECTINFO."MONOPOLYCODE_" is '车行代码';

comment on column WF_T_ACTIVITYOBJECTINFO."STATE_" is '处理状态（-2 重复添加 -1 不是有效的活动对象 0 未处理 1 成功 2跳过）';

comment on column WF_T_ACTIVITYOBJECTINFO."CREATED_AT_" is '创建时间';

comment on column WF_T_ACTIVITYOBJECTINFO."CREATED_BY_" is '创建者（用户、筛选规则、外部数据源ID）';

comment on column WF_T_ACTIVITYOBJECTINFO."VERIFIED_AT_" is '验证时间';

comment on column WF_T_ACTIVITYOBJECTINFO."COMID_" is '归属省级分公司';

comment on column WF_T_ACTIVITYOBJECTINFO."STATUS_" is '0 无效 1 有效';


create index "IDX_ACTOBJECTINFO_BATCHID"
    on WF_T_ACTIVITYOBJECTINFO using ubtree ("BATCHID_");

create table WF_T_ACTIVITYOBJECTINFO_INS
(
    "ID_"           varchar(50) not null,
    "BATCHID_"      varchar(50) not null,
    "CUSTID_"       varchar(30) not null,
    "OBJECTID_"     varchar(30) not null,
    "SYSTEMFLAG_"   varchar(4),
    "COMCODE_"      varchar(20),
    "MONOPOLYCODE_" varchar(40),
    "STATE_"        numeric(4)  not null,
    "CREATED_AT_"   timestamp   not null,
    "CREATED_BY_"   varchar(50) not null,
    "VERIFIED_AT_"  timestamp,
    "COMID_"        varchar(20) not null,
    "STATUS_"       varchar(4)  not null,
    "REMARK_"       varchar(200)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACTIVITYOBJECTINFO_INS is '活动对象正式表，保存经过处理的数据。例如经过数据权限筛选。';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."ID_" is '主键ID';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."BATCHID_" is '批次号';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."CUSTID_" is '活动对象对应的客户id';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."OBJECTID_" is '活动对象ID';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."SYSTEMFLAG_" is '对应营销系统中的SYSTEMFLAG';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."COMCODE_" is '活动对象归属的COMCODE（不一定是来自活动对象的属性，也可能是来自保单服务经理的属性）';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."MONOPOLYCODE_" is '车行代码';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."STATE_" is '处理状态（-2 重复添加 -1 不是有效的活动对象 0 未处理 1 成功 2跳过）';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."CREATED_AT_" is '创建时间';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."CREATED_BY_" is '创建者（用户、筛选规则、外部数据源ID）';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."VERIFIED_AT_" is '验证时间';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."COMID_" is '归属省级分公司';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."STATUS_" is '0 无效 1 有效';

comment on column WF_T_ACTIVITYOBJECTINFO_INS."REMARK_" is '处理详情';


create index "IDX_ACTOBJECTINFO_INS_BATCHID"
    on WF_T_ACTIVITYOBJECTINFO_INS using ubtree ("BATCHID_");

create table WF_T_ACTIVITYOBJECTMAIN
(
    "BATCHID_"       varchar(50) not null constraint "SYS_C0052955"
            primary key,
    "BATCH_COUNT_"   numeric(10) not null,
    "ACTIVITYID_"    varchar(30) not null,
    "STATE_"         numeric(4)  not null,
    "SUCCESS_COUNT_" numeric(10) not null,
    "SKIPPED_COUNT_" numeric(10) not null,
    "FAILED_COUNT_"  numeric(10) not null,
    "CHANNEL_"       varchar(10) not null,
    "COMID_"         varchar(20) not null,
    "CREATED_BY_"    varchar(50) not null,
    "CREATED_AT_"    timestamp   not null,
    "STATUS_"        varchar(4)  not null,
    "REMARK_"        varchar(3900)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACTIVITYOBJECTMAIN is '活动对象添加的批次表';

comment on column WF_T_ACTIVITYOBJECTMAIN."BATCHID_" is '批次号，也是批次的唯一标识。';

comment on column WF_T_ACTIVITYOBJECTMAIN."BATCH_COUNT_" is '本批次共包含多少数据';

comment on column WF_T_ACTIVITYOBJECTMAIN."ACTIVITYID_" is '本批次对应的活动ID';

comment on column WF_T_ACTIVITYOBJECTMAIN."STATE_" is '本批次的处理状态（-3 提送添加失败 -2 验证失败 -1 数据准备失败 0 未处理 1 已就绪【通过业务检查】 2 已推送到活动对象添加中间表） 3 没有可推送的数据';

comment on column WF_T_ACTIVITYOBJECTMAIN."SUCCESS_COUNT_" is '对于已处理的批次，记录成功处理的数目。';

comment on column WF_T_ACTIVITYOBJECTMAIN."SKIPPED_COUNT_" is '对于已处理的任务，跳过（不处理）的数量。';

comment on column WF_T_ACTIVITYOBJECTMAIN."FAILED_COUNT_" is '对于已经处理的批次，处理失败的数量。';

comment on column WF_T_ACTIVITYOBJECTMAIN."CHANNEL_" is '创建的渠道（手工添加、筛选规则添加、外部数据源ID）';

comment on column WF_T_ACTIVITYOBJECTMAIN."COMID_" is '省级机构代码';

comment on column WF_T_ACTIVITYOBJECTMAIN."STATUS_" is '0 无效 1 有效';

comment on column WF_T_ACTIVITYOBJECTMAIN."REMARK_" is '处理详情';


create index "WF_T_ACTIVITYOBJECTMAIN_1_"
    on WF_T_ACTIVITYOBJECTMAIN using ubtree ("ACTIVITYID_");

create index "WF_T_ACTIVITYOBJECTMAIN_2_"
    on WF_T_ACTIVITYOBJECTMAIN using ubtree ("COMID_");

create index "WF_T_ACTIVITYOBJECTMAIN_3_"
    on WF_T_ACTIVITYOBJECTMAIN using ubtree ("CREATED_BY_");

create table WF_T_ACTIVITYRESOURCE
(
    "RESOURCEPKGID"     varchar(30) not null,
    "RESOURCECODE"      varchar(30) not null,
    "AMOUNT"            numeric(1000, 53),
    "COMID"             varchar(8)  not null,
    "OPERATETIMEFORHIS" timestamp,
    "INSERTTIMEFORHIS"  timestamp,
    "UPDATERCODE"       varchar(10),
    "LOCKEDNUMBER"      numeric(1000, 53),
    "USEDNUMBER"        numeric(1000, 53),
    "COMCODE"           varchar(8),
    constraint "PK_WF_T_ACTIVITYRESOURCE"
        primary key ("RESOURCEPKGID", "RESOURCECODE")
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACTIVITYRESOURCE is 'WF_T_ActivityResource,活动资源配置表';

comment on column WF_T_ACTIVITYRESOURCE."RESOURCEPKGID" is 'ResourcePkgID,资源包ID';

comment on column WF_T_ACTIVITYRESOURCE."RESOURCECODE" is 'ResourceCode,资源代码';

comment on column WF_T_ACTIVITYRESOURCE."AMOUNT" is 'Amount,资源数量';

comment on column WF_T_ACTIVITYRESOURCE."COMID" is 'ComId,8位机构号';

comment on column WF_T_ACTIVITYRESOURCE."OPERATETIMEFORHIS" is 'OperateTimeForHis,操作时间';

comment on column WF_T_ACTIVITYRESOURCE."INSERTTIMEFORHIS" is 'InsertTimeForHis,插入时间';

comment on column WF_T_ACTIVITYRESOURCE."UPDATERCODE" is 'UpdaterCode,更新人';

comment on column WF_T_ACTIVITYRESOURCE."LOCKEDNUMBER" is 'LockedNumber,资源占用数量';

comment on column WF_T_ACTIVITYRESOURCE."USEDNUMBER" is 'UsedNumber,资源使用数量';

comment on column WF_T_ACTIVITYRESOURCE."COMCODE" is 'ComCode,归属机构代码';


create table WF_T_ACTIVITYTARGETFILTER
(
    "STRATEGYID"        varchar(30) not null constraint "PK_WF_T_ACTIVITYTARGETFILTER"
            primary key,
    "STRATEGYTYPE"      numeric(1000, 53),
    "ACTIVITYID"        varchar(30) not null,
    "PROCESSID"         varchar(30),
    "COMID"             varchar(8)  not null,
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "UPDATERCODE"       varchar(10),
    "COMCODE"           varchar(8),
    "QUERYCONDITIONS"   varchar(3900)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACTIVITYTARGETFILTER is 'WF_T_ActivityTargetFilter,活动对象筛选策略表';

comment on column WF_T_ACTIVITYTARGETFILTER."STRATEGYID" is 'StrategyID,筛选策略ID';

comment on column WF_T_ACTIVITYTARGETFILTER."STRATEGYTYPE" is 'StrategyType,筛选类型';

comment on column WF_T_ACTIVITYTARGETFILTER."ACTIVITYID" is 'ActivityID,活动ID';

comment on column WF_T_ACTIVITYTARGETFILTER."PROCESSID" is 'ProcessID,流程ID';

comment on column WF_T_ACTIVITYTARGETFILTER."COMID" is 'ComId,8位机构号';

comment on column WF_T_ACTIVITYTARGETFILTER."INSERTTIMEFORHIS" is 'InsertTimeForHis,插入时间';

comment on column WF_T_ACTIVITYTARGETFILTER."OPERATETIMEFORHIS" is 'OperateTimeForHis,更新时间';

comment on column WF_T_ACTIVITYTARGETFILTER."UPDATERCODE" is 'UpdaterCode,更新人';

comment on column WF_T_ACTIVITYTARGETFILTER."COMCODE" is 'ComCode,归属机构代码';

comment on column WF_T_ACTIVITYTARGETFILTER."QUERYCONDITIONS" is 'QueryConditions,筛选条件值';


create table WF_T_ACTPOLICYIMPBATCH
(
    "BATCHNO"           varchar(30) not null constraint "PK_WF_T_ACTPOLICYIMPBATCH"
            primary key,
    "BATCHNAME"         varchar(200),
    "IMPORTTYPE"        varchar(2),
    "ERRORNUM"          numeric(1000, 53),
    "SUCCESSNUM"        numeric(1000, 53),
    "COMID"             varchar(8)  not null,
    "COMCODE"           varchar(8),
    "BREAKSTATUS"       varchar(2),
    "VALIDSTATUS"       varchar(1),
    "CREATORCODE"       varchar(30),
    "INSERTTIMEFORHIS"  timestamp,
    "UPDATERCODE"       varchar(30),
    "OPERATETIMEFORHIS" timestamp,
    "SUMNUM"            numeric(1000, 53),
    "REMARK"            varchar(1000),
    "ACTIVITYID"        varchar(30),
    "PROCESSID"         varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACTPOLICYIMPBATCH is '客户导入批次表';

comment on column WF_T_ACTPOLICYIMPBATCH."BATCHNO" is 'BatchNo,批次号';

comment on column WF_T_ACTPOLICYIMPBATCH."BATCHNAME" is 'BatchName,导入批次名称';

comment on column WF_T_ACTPOLICYIMPBATCH."IMPORTTYPE" is 'ImportType 导入进度: I-初始状态 V-验证完成 T-加入活动完成 O-分配首节点完成 P-最后一步补数完成';

comment on column WF_T_ACTPOLICYIMPBATCH."ERRORNUM" is 'ErrorNum,失败数量';

comment on column WF_T_ACTPOLICYIMPBATCH."SUCCESSNUM" is 'SuccessNum,成功数量';

comment on column WF_T_ACTPOLICYIMPBATCH."COMID" is 'ComId,8位机构号';

comment on column WF_T_ACTPOLICYIMPBATCH."COMCODE" is 'ComCode,归属机构代码';

comment on column WF_T_ACTPOLICYIMPBATCH."BREAKSTATUS" is 'BreakStatus, 状态<I-初始状态;W-等待;R-执行中;V-验证完成;T-加入活动完成;O分配首节点完成;D-删除;F-已完成;E-执行错误;>';

comment on column WF_T_ACTPOLICYIMPBATCH."VALIDSTATUS" is 'ValidStatus,有效标志<0,无效;1,有效;>';

comment on column WF_T_ACTPOLICYIMPBATCH."CREATORCODE" is 'CreatorCode,创建人代码';

comment on column WF_T_ACTPOLICYIMPBATCH."INSERTTIMEFORHIS" is 'InsertTimeForHis,创建时间';

comment on column WF_T_ACTPOLICYIMPBATCH."UPDATERCODE" is 'UpdaterCode,更新人代码';

comment on column WF_T_ACTPOLICYIMPBATCH."OPERATETIMEFORHIS" is 'OperateTimeForHis,更新时间';

comment on column WF_T_ACTPOLICYIMPBATCH."SUMNUM" is 'SumNum,导入总数';

comment on column WF_T_ACTPOLICYIMPBATCH."REMARK" is 'remark 备注 记录一些导入时的信息';

comment on column WF_T_ACTPOLICYIMPBATCH."ACTIVITYID" is '活动ID';

comment on column WF_T_ACTPOLICYIMPBATCH."PROCESSID" is '流程ID';


create index "IDX_ACTPIB_BATCHNAME"
    on WF_T_ACTPOLICYIMPBATCH using ubtree ("BATCHNAME");

create index "IDX_ACTPIB_CREATORCODE"
    on WF_T_ACTPOLICYIMPBATCH using ubtree ("CREATORCODE");

create table WF_T_ACTPOLICYIMPINFO
(
    "IMPORTID"                  varchar(30) not null constraint "PK_WF_T_ACTPII"
            primary key,
    "BATCHNO"                   varchar(30),
    "POLICYNO"                  varchar(1000),
    "COMID"                     varchar(8)  not null,
    "COMCODE"                   varchar(1000),
    "CREATORCODE"               varchar(100),
    "DATASOURCE"                varchar(1000),
    "CHECKINFO"                 varchar(1000),
    "VALIDSTATUS"               varchar(1),
    "INSERTTIMEFORHIS"          timestamp,
    "UPDATERCODE"               varchar(10),
    "OPERATETIMEFORHIS"         timestamp,
    "BREAKINFO"                 varchar(1000),
    "BATCHDUPFLAG"              varchar(2),
    "CUSTID"                    varchar(100),
    "BPMPROCESSINSTANCEID"      varchar(80),
    "CHANNELSOURCE"             varchar(500),
    "CUSTOMERREMARK"            varchar(1000),
    "OPERATORCODE"              varchar(100),
    "ENTERPRISECONTACTIDNUMBER" varchar(60),
    "ENTERPRISECONTACTNAME"     varchar(200)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ACTPOLICYIMPINFO is '保单导入表';

comment on column WF_T_ACTPOLICYIMPINFO."IMPORTID" is 'ImportId,导入ID';

comment on column WF_T_ACTPOLICYIMPINFO."BATCHNO" is 'BatchNo,批次号';

comment on column WF_T_ACTPOLICYIMPINFO."POLICYNO" is '保单号';

comment on column WF_T_ACTPOLICYIMPINFO."COMID" is 'ComId,8位机构号';

comment on column WF_T_ACTPOLICYIMPINFO."COMCODE" is '归属机构';

comment on column WF_T_ACTPOLICYIMPINFO."CREATORCODE" is 'CreatorCode,创建人代码';

comment on column WF_T_ACTPOLICYIMPINFO."CHECKINFO" is 'CheckInfo,校验信息';

comment on column WF_T_ACTPOLICYIMPINFO."VALIDSTATUS" is 'ValidStatus,有效标志';

comment on column WF_T_ACTPOLICYIMPINFO."INSERTTIMEFORHIS" is 'InsertTimeForHis,创建时间';

comment on column WF_T_ACTPOLICYIMPINFO."UPDATERCODE" is 'UpdaterCode,更新人代码';

comment on column WF_T_ACTPOLICYIMPINFO."OPERATETIMEFORHIS" is 'OperateTimeForHis,更新时间';

comment on column WF_T_ACTPOLICYIMPINFO."BREAKINFO" is 'BrerakInfo,拆分状态';

comment on column WF_T_ACTPOLICYIMPINFO."BATCHDUPFLAG" is 'BatchDupFlag,批次内重复数据标志';

comment on column WF_T_ACTPOLICYIMPINFO."CUSTID" is '客户id';

comment on column WF_T_ACTPOLICYIMPINFO."CHANNELSOURCE" is '渠道来源';

comment on column WF_T_ACTPOLICYIMPINFO."CUSTOMERREMARK" is '客户导入备注';

comment on column WF_T_ACTPOLICYIMPINFO."OPERATORCODE" is '任务执行人';

comment on column WF_T_ACTPOLICYIMPINFO."ENTERPRISECONTACTIDNUMBER" is '企业客户联系人身份证号';


create index "IDX_ACTPII_CREATORCODE"
    on WF_T_ACTPOLICYIMPINFO using ubtree ("BATCHNO");

create table WF_T_ADDWXCUSTAPPLY
(
    "APPLYID"           varchar(100) not null constraint "PK_WF_T_ADDWXCUSTAPPLY"
            primary key,
    "CUSTID"            varchar(100),
    "CUSTNAME"          varchar(50),
    "IDENTIFYNO"        varchar(30),
    "LICENSENO"         varchar(30),
    "INSERTTIMEFORHIS"  timestamp    not null,
    "CREATORCODE"       varchar(50),
    "ADDAPPLYTYPE"      varchar(6),
    "ADDWXOATYPE"       varchar(6),
    "COMID"             varchar(8)   not null,
    "SUCCESSFLAG"       varchar(10),
    "OPERATETIMEFORHIS" timestamp,
    "POLICYNO"          varchar(30),
    "ENDDATE"           varchar(10),
    "PAYURL"            varchar(200),
    "PRICE"             varchar(20),
    "PROPOSALNO"        varchar(500),
    "RISKCODE"          varchar(60),
    "NETSALECOMID"      varchar(8),
    "PAYWAY"            varchar(8),
    "EXPIRETIME"        timestamp,
    "ACTIVITYID"        varchar(30)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ADDWXCUSTAPPLY is '添加微信客户申请表';

comment on column WF_T_ADDWXCUSTAPPLY."APPLYID" is '申请ID';

comment on column WF_T_ADDWXCUSTAPPLY."CUSTID" is '客户ID';

comment on column WF_T_ADDWXCUSTAPPLY."CUSTNAME" is '客户姓名';

comment on column WF_T_ADDWXCUSTAPPLY."IDENTIFYNO" is '证件号';

comment on column WF_T_ADDWXCUSTAPPLY."LICENSENO" is '车牌';

comment on column WF_T_ADDWXCUSTAPPLY."INSERTTIMEFORHIS" is '添加时间';

comment on column WF_T_ADDWXCUSTAPPLY."CREATORCODE" is '操作人';

comment on column WF_T_ADDWXCUSTAPPLY."ADDAPPLYTYPE" is '添加类型（1 加密code方式，2公众号方式）';

comment on column WF_T_ADDWXCUSTAPPLY."ADDWXOATYPE" is '公众号添加类型（1. 手机号，2 身份证）';

comment on column WF_T_ADDWXCUSTAPPLY."COMID" is '8位机构号';

comment on column WF_T_ADDWXCUSTAPPLY."SUCCESSFLAG" is '是否添加成功 （0-成功 1-失败 2-异常（通常是接口不通））';

comment on column WF_T_ADDWXCUSTAPPLY."OPERATETIMEFORHIS" is '更新时间';

comment on column WF_T_ADDWXCUSTAPPLY."POLICYNO" is '二维码支付关联保单号';

comment on column WF_T_ADDWXCUSTAPPLY."ENDDATE" is '终保日期字符串';

comment on column WF_T_ADDWXCUSTAPPLY."PAYURL" is 'e通支付链接';

comment on column WF_T_ADDWXCUSTAPPLY."PRICE" is '支付金额';

comment on column WF_T_ADDWXCUSTAPPLY."PROPOSALNO" is '投保单号';

comment on column WF_T_ADDWXCUSTAPPLY."RISKCODE" is '险种代码';

comment on column WF_T_ADDWXCUSTAPPLY."NETSALECOMID" is '网销添加客户归属8位机构号';

comment on column WF_T_ADDWXCUSTAPPLY."PAYWAY" is '支付方式，1为微信支付，2为支付宝支付';

comment on column WF_T_ADDWXCUSTAPPLY."ACTIVITYID" is '活动id';


create index "ADDWXCUSTAPPLY_CUSTID"
    on WF_T_ADDWXCUSTAPPLY using ubtree ("CUSTID");

create index "ADDWXCUSTAPPLY_IDENTIFYNO"
    on WF_T_ADDWXCUSTAPPLY using ubtree ("IDENTIFYNO");

create index "ADDWXCUSTAPPLY_INSERTTIME"
    on WF_T_ADDWXCUSTAPPLY using ubtree ("INSERTTIMEFORHIS");

create index "ADDWXCUSTAPPLY_LICENSENO"
    on WF_T_ADDWXCUSTAPPLY using ubtree ("LICENSENO");

create table WF_T_ANNUAL
(
    "ANNUALID"           varchar(30) not null constraint "PK_WF_T_ANNUAL"
            primary key,
    "CUSTID"             varchar(30),
    "LICENSENO"          varchar(40),
    "FRAMENO"            varchar(30),
    "ANNUALTIME"         timestamp,
    "ANNUALCONDUCTPLACE" varchar(250),
    "VALIDSTATUS"        varchar(1),
    "INSERTTIMEFORHIS"   timestamp,
    "CREATORCODE"        varchar(10),
    "OPERATETIMEFORHIS"  timestamp,
    "UPDATERCODE"        varchar(10),
    "COMID"              varchar(8)  not null,
    "COMCODE"            varchar(8)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_ANNUAL is '年审办理表';

comment on column WF_T_ANNUAL."ANNUALID" is 'AnnualID,年审ID';

comment on column WF_T_ANNUAL."CUSTID" is 'CustID,客户ID';

comment on column WF_T_ANNUAL."LICENSENO" is 'LicenseNo,车牌号';

comment on column WF_T_ANNUAL."FRAMENO" is 'FrameNo,车架号';

comment on column WF_T_ANNUAL."ANNUALTIME" is 'AnnualTime,年审日期';

comment on column WF_T_ANNUAL."ANNUALCONDUCTPLACE" is 'AnnualConductPlace,年审办理地点';

comment on column WF_T_ANNUAL."VALIDSTATUS" is 'ValidStatus,有效状态位';

comment on column WF_T_ANNUAL."INSERTTIMEFORHIS" is 'InsertTimeForHis,插入时间';

comment on column WF_T_ANNUAL."CREATORCODE" is 'CreatorCode,创建人代码';

comment on column WF_T_ANNUAL."OPERATETIMEFORHIS" is 'OperateTimeForHis,操作时间';

comment on column WF_T_ANNUAL."UPDATERCODE" is 'UpdaterCode,更新人代码';

comment on column WF_T_ANNUAL."COMID" is 'ComId,8位机构号';

comment on column WF_T_ANNUAL."COMCODE" is 'ComCode,归属机构代码';


create index "IDX_WF_T_ANNUAL_CUSTID"
    on WF_T_ANNUAL using ubtree ("CUSTID");

create table WF_T_APPOINTMENTINFO
(
    "APPOINTMENTINFOID" varchar(100) not null constraint "SYS_C0054396"
            primary key,
    "PIID"              varchar(200),
    "POLICYNO"          varchar(150),
    "APPOINTMENTPHONE"  varchar(100),
    "APPOINTMENTDATE"   timestamp,
    "COMID"             varchar(50),
    "COMCODE"           varchar(50),
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "MESSAGE"           varchar(255)
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_APPOINTMENTINFO is '接收预约信息表 （WF_T_APPOINTMENTINFO）';

comment on column WF_T_APPOINTMENTINFO."APPOINTMENTINFOID" is 'id主键';

comment on column WF_T_APPOINTMENTINFO."PIID" is 'piid';

comment on column WF_T_APPOINTMENTINFO."POLICYNO" is '保单号';

comment on column WF_T_APPOINTMENTINFO."APPOINTMENTPHONE" is '预约的联系电话';

comment on column WF_T_APPOINTMENTINFO."APPOINTMENTDATE" is '预约时间';

comment on column WF_T_APPOINTMENTINFO."COMID" is '省机构id';

comment on column WF_T_APPOINTMENTINFO."COMCODE" is '机构id';

comment on column WF_T_APPOINTMENTINFO."INSERTTIMEFORHIS" is '插入时间';

comment on column WF_T_APPOINTMENTINFO."OPERATETIMEFORHIS" is '更新时间';

comment on column WF_T_APPOINTMENTINFO."MESSAGE" is '预约消息';


create table WF_T_APPOINTMENTPUSH
(
    "PUSHID"            varchar(50) not null constraint "SYS_C001164500"
            primary key,
    "CUSTID"            varchar(100),
    "POLICYNO"          varchar(150),
    "LICENSENO"         varchar(100),
    "FLAG"              varchar(255),
    "COMID"             varchar(50),
    "COMCODE"           varchar(50),
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_APPOINTMENTPUSH is '推送客户信息表（WF_T_APPOINTMENTPUSH）';

comment on column WF_T_APPOINTMENTPUSH."PUSHID" is 'id主键';

comment on column WF_T_APPOINTMENTPUSH."CUSTID" is '客户id';

comment on column WF_T_APPOINTMENTPUSH."POLICYNO" is '保单号';

comment on column WF_T_APPOINTMENTPUSH."LICENSENO" is '车牌号';

comment on column WF_T_APPOINTMENTPUSH."FLAG" is '推送标志（0：未推送、1：30天推送成功、2、25天推送成功、3、3天推送成功、4、推送完成、5、推送失败））';

comment on column WF_T_APPOINTMENTPUSH."COMID" is '省机构id';

comment on column WF_T_APPOINTMENTPUSH."COMCODE" is '机构id';

comment on column WF_T_APPOINTMENTPUSH."INSERTTIMEFORHIS" is '插入时间';

comment on column WF_T_APPOINTMENTPUSH."OPERATETIMEFORHIS" is '更新时间';


create index "IDX_APP_INSERTTIMEFORHIS"
    on WF_T_APPOINTMENTPUSH using ubtree ("INSERTTIMEFORHIS");

create table WF_T_AUTOASSIGNFAIL
(
    "PIID"             varchar(30) not null constraint "PK_WFTAUTOASSIGNFAIL"
            primary key,
    "TASKID"           varchar(30),
    "COMID"            varchar(8),
    "INSERTTIMEFORHIS" timestamp
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_AUTOASSIGNFAIL is '自动分配失败数据表';

comment on column WF_T_AUTOASSIGNFAIL."PIID" is '流程实例ID，主键';

comment on column WF_T_AUTOASSIGNFAIL."TASKID" is '任务ID';

comment on column WF_T_AUTOASSIGNFAIL."COMID" is '省级机构代码';

comment on column WF_T_AUTOASSIGNFAIL."INSERTTIMEFORHIS" is '插入日期时间';


create index "IDX_AUTOASSIGNFAIL_COMID"
    on WF_T_AUTOASSIGNFAIL using ubtree ("COMID");

create table WF_T_BUSINESSGROUPPOLICY
(
    "BUSINESSNO"         varchar(30) not null constraint "PK_BUSINESSGROUPPOLICY"
            primary key,
    "COMID"              varchar(8),
    "COMIDNAME"          varchar(1000),
    "COMCODE"            varchar(8),
    "COMCODENAME"        varchar(1000),
    "PREFECTURENAME"     varchar(1000),
    "COUNTYNAME"         varchar(1000),
    "POLICYNO"           varchar(30),
    "INSUREDCODE"        varchar(30),
    "INSUREDNAME"        varchar(250),
    "INSURED1CODE"       varchar(30),
    "INSURED1NAME"       varchar(250),
    "RISKCODE"           varchar(30),
    "RISKNAME"           varchar(250),
    "CLASSCODE"          varchar(30),
    "CLASSNAME"          varchar(250),
    "WITHINPREMIUM"      numeric(14, 2),
    "HANDLERCODE"        varchar(30),
    "HANDLERNAME"        varchar(100),
    "GROUPCODE"          varchar(30),
    "STARTDATE"          timestamp,
    "ENDDATE"            timestamp,
    "SUMPREMIUM"         numeric(14, 2),
    "MANAGERCODE"        varchar(30),
    "BELONGTEAMTYPE"     varchar(30),
    "BELONGTEAMCODE"     varchar(30),
    "SIGNBELONGTEAMTYPE" varchar(30),
    "SIGNBELONGTEAMCODE" varchar(30),
    "INSERTTIMEFORHIS"   timestamp,
    "UPDATERCODE"        varchar(16),
    "CREATORCODE"        varchar(16),
    "OPERATETIMEFORHIS"  timestamp
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_BUSINESSGROUPPOLICY is 'wf_t_businessGroupPolicy,商团保单表';

comment on column WF_T_BUSINESSGROUPPOLICY."BUSINESSNO" is 'businessno,商团保单id';

comment on column WF_T_BUSINESSGROUPPOLICY."COMID" is 'comid,省分公司';

comment on column WF_T_BUSINESSGROUPPOLICY."COMIDNAME" is '省分公司名称';

comment on column WF_T_BUSINESSGROUPPOLICY."COMCODENAME" is '归属机构名称';

comment on column WF_T_BUSINESSGROUPPOLICY."PREFECTURENAME" is '地市公司';

comment on column WF_T_BUSINESSGROUPPOLICY."COUNTYNAME" is '县区支公司';

comment on column WF_T_BUSINESSGROUPPOLICY."POLICYNO" is 'policyno,保单号';

comment on column WF_T_BUSINESSGROUPPOLICY."INSUREDCODE" is 'insuredCode,投保人';

comment on column WF_T_BUSINESSGROUPPOLICY."INSUREDNAME" is '投保人名称';

comment on column WF_T_BUSINESSGROUPPOLICY."INSURED1CODE" is 'insured1Code,被保险人代码';

comment on column WF_T_BUSINESSGROUPPOLICY."INSURED1NAME" is '被保人名称';

comment on column WF_T_BUSINESSGROUPPOLICY."RISKNAME" is '险种名称';

comment on column WF_T_BUSINESSGROUPPOLICY."CLASSNAME" is '险类名称';


create index "IDX_BUSINESS_ENDDATE"
    on WF_T_BUSINESSGROUPPOLICY using ubtree ("ENDDATE");

create index "IDX_BUSINESS_INSURED1NAME"
    on WF_T_BUSINESSGROUPPOLICY using ubtree ("INSURED1NAME");

create index "IDX_BUSINESS_INSUREDNAME"
    on WF_T_BUSINESSGROUPPOLICY using ubtree ("INSUREDNAME");

create index "IDX_BUSINESS_POLICYNO"
    on WF_T_BUSINESSGROUPPOLICY using ubtree ("POLICYNO");

create index "IDX_BUSINESS_STARTDATE"
    on WF_T_BUSINESSGROUPPOLICY using ubtree ("STARTDATE");

create table WF_T_CARLATESTPOLICY
(
    "ITEMID"            varchar(30) not null,
    "CARID"             varchar(30) not null,
    "ENDDATE"           timestamp,
    "ENDMONTH"          varchar(8),
    "ENDDAY"            varchar(8),
    "LICENSENO"         varchar(40),
    "REMARK"            varchar(255),
    "COMID"             varchar(8)  not null,
    "COMCODE"           varchar(24),
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "UPDATERCODE"       varchar(16),
    "POLICYNO"          varchar(30),
    "CUSTOMERCNAME"     varchar(200),
    "STATUSTYPE"        varchar(2),
    constraint "PK_WF_TARLATESTPOLICY_0726"
        primary key ("ITEMID", "COMID")
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_CARLATESTPOLICY is '车辆最近保单表';

comment on column WF_T_CARLATESTPOLICY."ITEMID" is 'ItemID';

comment on column WF_T_CARLATESTPOLICY."CARID" is 'CarID，车辆ID';

comment on column WF_T_CARLATESTPOLICY."ENDDATE" is 'EndDate,终保日期';

comment on column WF_T_CARLATESTPOLICY."ENDMONTH" is 'EndMonth，终保月份';

comment on column WF_T_CARLATESTPOLICY."ENDDAY" is 'EndDay，终保日';

comment on column WF_T_CARLATESTPOLICY."LICENSENO" is 'LicenseNo，车牌号';

comment on column WF_T_CARLATESTPOLICY."REMARK" is 'Remark，备注';

comment on column WF_T_CARLATESTPOLICY."COMID" is 'ComID，ComID';

comment on column WF_T_CARLATESTPOLICY."COMCODE" is 'ComCode，ComCode';

comment on column WF_T_CARLATESTPOLICY."INSERTTIMEFORHIS" is 'InsertTimeForHis，创建时间';

comment on column WF_T_CARLATESTPOLICY."OPERATETIMEFORHIS" is 'OperatorTimeForHis，更新时间';

comment on column WF_T_CARLATESTPOLICY."UPDATERCODE" is 'UpdaterCode，更新人';

comment on column WF_T_CARLATESTPOLICY."POLICYNO" is 'PolicyNo，保单号';

comment on column WF_T_CARLATESTPOLICY."CUSTOMERCNAME" is 'CustomerCName，客户姓名';

comment on column WF_T_CARLATESTPOLICY."STATUSTYPE" is 'StatusType，客户状态<-1,未明确;01,在保客户;02,潜在客户;03,脱保客户;99,其他;>';


create index "CARLATEST_CARID_POLICYNO"
    on WF_T_CARLATESTPOLICY using ubtree ("CARID", "POLICYNO");

create index "IDX_CARLATESTPOLICY_CARID_0726"
    on WF_T_CARLATESTPOLICY using ubtree ("CARID");

create index "IDX_CARLATESTPOLICY_ENDDATE_0726"
    on WF_T_CARLATESTPOLICY using ubtree ("ENDDATE");

create index "IDX_WF_CARLATESTPOLICY_1_0726"
    on WF_T_CARLATESTPOLICY using ubtree ("POLICYNO");

create unique index "PK_WF_T_CARLATESTPOLICY_0726"
    on WF_T_CARLATESTPOLICY using ubtree ("ITEMID", "COMID");

create table WF_T_CARLATESTPOLICY_BACKUP
(
    "ITEMID"            varchar(30) not null,
    "CARID"             varchar(30) not null,
    "ENDDATE"           timestamp,
    "ENDMONTH"          varchar(8),
    "ENDDAY"            varchar(8),
    "LICENSENO"         varchar(40),
    "REMARK"            varchar(255),
    "COMID"             varchar(8)  not null,
    "COMCODE"           varchar(24),
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "UPDATERCODE"       varchar(16),
    "POLICYNO"          varchar(30),
    "CUSTOMERCNAME"     varchar(200),
    "STATUSTYPE"        varchar(2),
    constraint "PK_CARLATESTPOLICY_BACKUP"
        primary key ("ITEMID", "COMID")
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_CARLATESTPOLICY_BACKUP is '车辆最近保单表';

comment on column WF_T_CARLATESTPOLICY_BACKUP."ITEMID" is 'ItemID';

comment on column WF_T_CARLATESTPOLICY_BACKUP."CARID" is 'CarID，车辆ID';

comment on column WF_T_CARLATESTPOLICY_BACKUP."ENDDATE" is 'EndDate,终保日期';

comment on column WF_T_CARLATESTPOLICY_BACKUP."ENDMONTH" is 'EndMonth，终保月份';

comment on column WF_T_CARLATESTPOLICY_BACKUP."ENDDAY" is 'EndDay，终保日';

comment on column WF_T_CARLATESTPOLICY_BACKUP."LICENSENO" is 'LicenseNo，车牌号';

comment on column WF_T_CARLATESTPOLICY_BACKUP."REMARK" is 'Remark，备注';

comment on column WF_T_CARLATESTPOLICY_BACKUP."COMID" is 'ComID，ComID';

comment on column WF_T_CARLATESTPOLICY_BACKUP."COMCODE" is 'ComCode，ComCode';

comment on column WF_T_CARLATESTPOLICY_BACKUP."INSERTTIMEFORHIS" is 'InsertTimeForHis，创建时间';

comment on column WF_T_CARLATESTPOLICY_BACKUP."OPERATETIMEFORHIS" is 'OperatorTimeForHis，更新时间';

comment on column WF_T_CARLATESTPOLICY_BACKUP."UPDATERCODE" is 'UpdaterCode，更新人';

comment on column WF_T_CARLATESTPOLICY_BACKUP."POLICYNO" is 'PolicyNo，保单号';

comment on column WF_T_CARLATESTPOLICY_BACKUP."CUSTOMERCNAME" is 'CustomerCName，客户姓名';

comment on column WF_T_CARLATESTPOLICY_BACKUP."STATUSTYPE" is 'StatusType，客户状态<-1,未明确;01,在保客户;02,潜在客户;03,脱保客户;99,其他;>';


create index "IDX_CARLATESTPOLICY_BK_CARID"
    on WF_T_CARLATESTPOLICY_BACKUP using ubtree ("CARID");

create index "IDX_CARLATESTPOLICY_BK_ENDDATE"
    on WF_T_CARLATESTPOLICY_BACKUP using ubtree ("ENDDATE");

create index "IDX_CARLATESTPOLICY_BK_PN"
    on WF_T_CARLATESTPOLICY_BACKUP using ubtree ("POLICYNO");

create table WF_T_CARLATESTPOLICYCLUE
(
    "ITEMID"            varchar(30) not null,
    "CARID"             varchar(30) not null,
    "ENDDATE"           timestamp,
    "ENDMONTH"          varchar(8),
    "ENDDAY"            varchar(8),
    "LICENSENO"         varchar(40),
    "REMARK"            varchar(255),
    "COMID"             varchar(8)  not null,
    "COMCODE"           varchar(24),
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "UPDATERCODE"       varchar(16),
    "POLICYNO"          varchar(30),
    "CUSTOMERCNAME"     varchar(200),
    "STATUSTYPE"        varchar(2),
    constraint "PK_WF_TARLATESTPOLICYCLUE"
        primary key ("ITEMID", "COMID")
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_CARLATESTPOLICYCLUE is '销售线索车辆最近保单表';

comment on column WF_T_CARLATESTPOLICYCLUE."ITEMID" is 'ItemID';

comment on column WF_T_CARLATESTPOLICYCLUE."CARID" is 'CarID，车辆ID';

comment on column WF_T_CARLATESTPOLICYCLUE."ENDDATE" is 'EndDate,终保日期';

comment on column WF_T_CARLATESTPOLICYCLUE."ENDMONTH" is 'EndMonth，终保月份';

comment on column WF_T_CARLATESTPOLICYCLUE."ENDDAY" is 'EndDay，终保日';

comment on column WF_T_CARLATESTPOLICYCLUE."LICENSENO" is 'LicenseNo，车牌号';

comment on column WF_T_CARLATESTPOLICYCLUE."REMARK" is 'Remark，备注';

comment on column WF_T_CARLATESTPOLICYCLUE."COMID" is 'ComID，ComID';

comment on column WF_T_CARLATESTPOLICYCLUE."COMCODE" is 'ComCode，ComCode';

comment on column WF_T_CARLATESTPOLICYCLUE."INSERTTIMEFORHIS" is 'InsertTimeForHis，创建时间';

comment on column WF_T_CARLATESTPOLICYCLUE."OPERATETIMEFORHIS" is 'OperatorTimeForHis，更新时间';

comment on column WF_T_CARLATESTPOLICYCLUE."UPDATERCODE" is 'UpdaterCode，更新人';

comment on column WF_T_CARLATESTPOLICYCLUE."POLICYNO" is 'PolicyNo，保单号';

comment on column WF_T_CARLATESTPOLICYCLUE."CUSTOMERCNAME" is 'CustomerCName，客户姓名';

comment on column WF_T_CARLATESTPOLICYCLUE."STATUSTYPE" is 'StatusType，客户状态<-1,未明确;01,在保客户;02,潜在客户;03,脱保客户;99,其他;>';


create index "IDX_CARLATESTPOLICYCLUE_CARID"
    on WF_T_CARLATESTPOLICYCLUE using ubtree ("CARID");

create index "IDX_CARLATESTPOLICYCLUE_EDATE"
    on WF_T_CARLATESTPOLICYCLUE using ubtree ("ENDDATE");

create index "IDX_WF_CARLATESTPOLICYCLUE_1"
    on WF_T_CARLATESTPOLICYCLUE using ubtree ("POLICYNO");

create table WF_T_CARPOLICYDATACLEAN
(
    "FRAMENO"           varchar(60),
    "COMID"             varchar(8)  not null,
    "COMCODE"           varchar(8),
    "CUSTID"            varchar(30),
    "CARID"             varchar(30),
    "POLICYNO"          varchar(66),
    "ENDDATE"           timestamp,
    "LICENSENO"         varchar(60),
    "VINNO"             varchar(60) not null,
    "INSERTTIMEFORHIS"  timestamp,
    "OPERATETIMEFORHIS" timestamp,
    "LOADTIME"          timestamp,
    "ENROLLDATE"        timestamp,
    "VALIDSTATUS"       varchar(1),
    "CUSTOMERCNAME"     varchar(200),
    "IDENTIFYTYPE"      varchar(30),
    "IDENTIFYNUMBER"    varchar(60),
    "STARTDATE"         timestamp,
    "RENEWALSTATUS"     varchar(2),
    constraint "WF_PK_CARPOLICYDATACLEAN"
        primary key ("VINNO", "COMID")
)
with (orientation = row, compression = no, storage_type = USTORE, segment = off);

comment on table WF_T_CARPOLICYDATACLEAN is '车辆保单数据清洗';

comment on column WF_T_CARPOLICYDATACLEAN."FRAMENO" is '车架号';

comment on column WF_T_CARPOLICYDATACLEAN."COMID" is '8位省机构号';

comment on column WF_T_CARPOLICYDATACLEAN."COMCODE" is '8位机构号';

comment on column WF_T_CARPOLICYDATACLEAN."CUSTID" is '客户ID';

comment on column WF_T_CARPOLICYDATACLEAN."CARID" is '车辆ID';

comment on column WF_T_CARPOLICYDATACLEAN."POLICYNO" is '保单号';

comment on column WF_T_CARPOLICYDATACLEAN."ENDDATE" is '终保日期';

comment on column WF_T_CARPOLICYDATACLEAN."LICENSENO" is '车牌号';

comment on column WF_T_CARPOLICYDATACLEAN."VINNO" is 'VIN号';

comment on column WF_T_CARPOLICYDATACLEAN."INSERTTIMEFORHIS" is '插入时间';

comment on column WF_T_CARPOLICYDATACLEAN."OPERATETIMEFORHIS" is '更新时间';

comment on column WF_T_CARPOLICYDATACLEAN."LOADTIME" is '装载时间';

comment on column WF_T_CARPOLICYDATACLEAN."ENROLLDATE" is '初登日期';

comment on column WF_T_CARPOLICYDATACLEAN."VALIDSTATUS" is '有效标志 1-有效，0-无效';

comment on column WF_T_CARPOLICYDATACLEAN."CUSTOMERCNAME" is '客户姓名';

comment on column WF_T_CARPOLICYDATACLEAN."IDENTIFYTYPE" is '证件类型';

comment on column WF_T_CARPOLICYDATACLEAN."IDENTIFYNUMBER" is '证件号';

comment on column WF_T_CARPOLICYDATACLEAN."STARTDATE" is '起保日期';

comment on column WF_T_CARPOLICYDATACLEAN."RENEWALSTATUS" is '续保状态：1 兜底未成单';


create index "IDX_CARPOLICYDATACLEAN_COMCODE"
    on WF_T_CARPOLICYDATACLEAN using ubtree ("COMCODE");

create index "IDX_CARPOLICYDATACLEAN_ENDDATE"
    on WF_T_CARPOLICYDATACLEAN using ubtree ("ENDDATE");

create index "IDX_CARPOLICYDATACLEAN_FRAMENO"
    on WF_T_CARPOLICYDATACLEAN using ubtree ("FRAMENO");

create index "IDX_CARPOLICYDATACLEAN_LICENSE"
    on WF_T_CARPOLICYDATACLEAN using ubtree ("LICENSENO");

create index "IDX_CARPOLICYDATACLEAN_POLICY"
    on WF_T_CARPOLICYDATACLEAN using ubtree ("POLICYNO");

create index "IDX_CARPOLICYDC_ENROLLDATE"
    on WF_T_CARPOLICYDATACLEAN using ubtree ("ENROLLDATE");


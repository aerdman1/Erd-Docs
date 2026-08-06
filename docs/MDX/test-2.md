---
title: test
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
<Table>
  <thead>
    <tr>
      <th>
        Error Code
      </th>

      <th>
        Error Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ADVANCED_CRITERIA_MUST_BE_PROVIDED
      </td>

      <td>
        when advanced criteria is missing for advanced audience
      </td>
    </tr>

    <tr>
      <td>
        DVANCED_CRITERIA_ONLY_ALLOWED_IN_ADVANCED_AUDIENCE
      </td>

      <td>
        when advanced criteria is passed for audiences other than advanced
      </td>
    </tr>

    <tr>
      <td>
        ADVERTISER_DOES_NOT_HAVE_ACCESS_TO_SEED_AUDIENCE_ID
      </td>

      <td>
        when advertiser does not have access to the given audience id
      </td>
    </tr>

    <tr>
      <td>
        AGE_VALUES_NOT_IN_CORRECT_ORDER
      </td>

      <td>
        Age values are not in correct order in Rule Based criteria
      </td>
    </tr>

    <tr>
      <td>
        ALL_AGE_VALUES_TOGETHER_ARE_NOT_ALLOWED
      </td>

      <td>
        All Age values are not allowed together
      </td>
    </tr>

    <tr>
      <td>
        ALL_INCOME_VALUES_TOGETHER_ARE_NOT_ALLOWED
      </td>

      <td>
        All Income values are not allowed together
      </td>
    </tr>

    <tr>
      <td>
        AUDIENCE_ALREADY_EXIST_WITH_GIVEN_NAME
      </td>

      <td>
        when provided audience name already exists
      </td>
    </tr>

    <tr>
      <td>
        AUDIENCE_ATTRIBUTE_CANNOT_BE_UPDATED
      </td>

      <td>
        when user tries to update audience attribute
      </td>
    </tr>

    <tr>
      <td>
        AUDIENCE_CRITERIA_MUST_BE_PROVIDED
      </td>

      <td>
        when audience criteria is missing in audience creation/updation request
      </td>
    </tr>

    <tr>
      <td>
        AUDIENCE_CRITERIA_MUST_HAVE_ATLEAST_ONE_SEED_AUDIENCE
      </td>

      <td>
        Provide atleast one seed audience in Advanced Audience Crtieria
      </td>
    </tr>

    <tr>
      <td>
        AUDIENCE_DEFINITION_AND_ATTRIBUTE_ONLY_ALLOWED_TOGETHER
      </td>

      <td>
        for audience patch, attribute and definition should be provided together
      </td>
    </tr>

    <tr>
      <td>
        AUDIENCE_ID_NOT_FOUND_FOR_REQUESTED_ADVERTISER
      </td>

      <td>
        Audience Id provided in advanced criteria does not exist for the advertiser
      </td>
    </tr>

    <tr>
      <td>
        AUDIENCE_NOT_FOUND
      </td>

      <td>
        Audience provided is not found
      </td>
    </tr>

    <tr>
      <td>
        AUDIENCE_OBJECTIVE_TEXT_MANDATORY_FOR_OTHER_AUDIENCE_OBJECTIVE
      </td>

      <td>
        audience objective text is not passed when audience objective selected is "OTHER"
      </td>
    </tr>

    <tr>
      <td>
        BRAND_AFFINITY_CRITERIA_MUST_BE_PROVIDED


      </td>

      <td>
        when brand affinity criteria is missing for brand affinity audience
      </td>
    </tr>

    <tr>
      <td>
        BRAND_AFFINITY_CRITERIA_NOT_ALLOWED_FOR_ITEM_PROPENSITY_AUDIENCE
      </td>

      <td>
        when brand affinity criteria provided for item propensity audience
      </td>
    </tr>

    <tr>
      <td>
        BRAND_AFFINITY_CRITERIA_NOT_ALLOWED_FOR_LOOK_ALIKE_AUDIENCE
      </td>

      <td>
        when brand affinity criteria provided for lookalike audience
      </td>
    </tr>

    <tr>
      <td>
        BRAND_AFFINITY_CRITERIA_ONLY_ALLOWED_IN_BRAND_AFFINITY_AUDIENCE

        PROVIDE_EITHER_OFFSET_OR_DATE_RANGE
      </td>

      <td>
        when brand affinity criteria is passed for audiences other than brand affinity
      </td>
    </tr>

    <tr>
      <td>
        BRANDS_CANNOT_BE_EMPTY_OR_NULL
      </td>

      <td>
        when provided brands is empty or null for brand affinity audience
      </td>
    </tr>

    <tr>
      <td>
        BUILT_AT_OR_SIZE_DETAILS_NOT_FOUND_FOR_AUDIENCE
      </td>

      <td>
        Either the audience is not in built state or size details are not found when requested in Audience Estimate api
      </td>
    </tr>

    <tr>
      <td>
        CATEGORIES_SHOULD_NOT_BE_EMPTY_OR_NULL
      </td>

      <td>
        when provided categories are empty or null for brand affinity audience
      </td>
    </tr>

    <tr>
      <td>
        CATEGORY_BASED_PROPENSITY_AUDIENCE_NOT_SUPPORTED_FOR_LOOKALIKE_AUDIENCE
      </td>

      <td>
        when provided seed audience id is of category based item propensity audience
      </td>
    </tr>

    <tr>
      <td>
        CITY_OR_STATE_NOT_ALLOWED_WITH_DMA


      </td>

      <td>
        when city or state node provided with DMA node
      </td>
    </tr>

    <tr>
      <td>
        DATE_RANGE_ONLY_SUPPORTED_FOR_LIVE_OR_COMPLETED_CAMPAIGN
      </td>

      <td>
        Date range filters are only applicable when campaign status is LIVE or COMPLETED
      </td>
    </tr>

    <tr>
      <td>
        DEMOGRAPHICS_CRITERIA_NOT_ALLOWED_FOR_BRAND_AFFINITY_AUDIENCE
      </td>

      <td>
        when demograhics provided for brand affinity audience
      </td>
    </tr>

    <tr>
      <td>
        DEMOGRAPHICS_CRITERIA_NOT_ALLOWED_FOR_ITEM_PROPENSITY_AUDIENCE
      </td>

      <td>
        when demograhics are provided in item propensity audience
      </td>
    </tr>

    <tr>
      <td>
        DEMOGRAPHICS_CRITERIA_NOT_ALLOWED_FOR_LOOK_ALIKE_AUDIENCE


      </td>

      <td>
        when demographics provided in lookalike audience
      </td>
    </tr>

    <tr>
      <td>
        DEMOGRAPHICS_CRITERIA_ONLY_ALLOWED_IN_RULE_BASED_AUDIENCE
      </td>

      <td>
        when demographics are passed for audiences other than rule based
      </td>
    </tr>

    <tr>
      <td>
        DESCRIPTION_LIMIT_EXCEEDED
      </td>

      <td>
        when provided description exceeds 120 chars
      </td>
    </tr>

    <tr>
      <td>
        DUPLICATE_BRANDS_NOT_ALLOWED
      </td>

      <td>
        when duplicate brands are provided in brand affinity request
      </td>
    </tr>

    <tr>
      <td>
        DUPLICATE_TAXONOMIES_NOT_ALLOWED
      </td>

      <td>
        when duplicate taxonomies are provided in brand affinity request
      </td>
    </tr>

    <tr>
      <td>
        EITHER_SEED_AUDIENCE_DOES_NOT_EXIST_OR_NOT_ACCESSIBLE
      </td>

      <td>
        Seed Audience Id provided in advanced criteria does not exist or the advertiser does not have enough access 
      </td>
    </tr>

    <tr>
      <td>
        EMPTY_ITEMSET


      </td>

      <td>
        when provided itemset id is empty
      </td>
    </tr>

    <tr>
      <td>
        END_OFFSET_DATE_MUST_BE_LATER_THAN_START_OFFSET_DATE
      </td>

      <td>
        when provided end offset date is greater than start offset date
      </td>
    </tr>

    <tr>
      <td>
        EXCLUDE_SHOULD_HAVE_ATLEAST_ONE_SEED_AUDIENCE


      </td>

      <td>
        Exclude criteria is requested should have atleast one seed audience
      </td>
    </tr>

    <tr>
      <td>
        FIELD_ATTRIBUTE_MANDATORY_WITH_AUDIENCE_DEFINITION
      </td>

      <td>
        Attribute Filed is mandatory in Estimate request when Audience Definition is passed
      </td>
    </tr>

    <tr>
      <td>
        FIELD_AUDIENCE_TYPE_MANDATORY_WITH_AUDIENCE_DEFINITION
      </td>

      <td>
        Audience Type Field is mandatory in Estimate request when Audience Definition is passed
      </td>
    </tr>

    <tr>
      <td>
        FIELD_ITEMSET_IDS_CANNOT_BE_EMPTY_OR_NULL
      </td>

      <td>
        when itemset ids is null or empty
      </td>
    </tr>

    <tr>
      <td>
        FIELD_PLATFORMS_CANNOT_BE_EMPTY_OR_NULL
      </td>

      <td>
        when platforms provided is either empty or null
      </td>
    </tr>

    <tr>
      <td>
        FILTER_AUDIENCE_IDS_LIMIT_EXCEEDED
      </td>

      <td>
        when more than 10 audience ids are passed in filter\[audienceId] 
      </td>
    </tr>

    <tr>
      <td>
        FILTER_NAME_LIMIT_EXCEEDED
      </td>

      <td>
        when more than 5 names are passed in filter\[name] 
      </td>
    </tr>

    <tr>
      <td>
        FOR_REQUESTED_DATE_SIZE_NOT_FOUND_FOR_AUDIENCE
      </td>

      <td>
        Audience Size is not found for requested date
      </td>
    </tr>

    <tr>
      <td>
        FREQUENCY_AND_PERCENTILE_NOT_ALLOWED_TOGETHER
      </td>

      <td>
        when frequency and percentile both are provided in rule based request
      </td>
    </tr>

    <tr>
      <td>
        GEO_TARGETS_CRITERIA_NOT_ALLOWED_FOR_BRAND_AFFINITY_AUDIENCE
      </td>

      <td>
        when geo targets provided for brand affinity audience
      </td>
    </tr>

    <tr>
      <td>
        GEO_TARGETS_CRITERIA_NOT_ALLOWED_FOR_ITEM_PROPENSITY_AUDIENCE
      </td>

      <td>
        when geo targets are provided in item propensity audience
      </td>
    </tr>

    <tr>
      <td>
        GEO_TARGETS_CRITERIA_NOT_ALLOWED_FOR_LOOK_ALIKE_AUDIENCE


      </td>

      <td>
        when geo targets provided in lookalike audience
      </td>
    </tr>

    <tr>
      <td>
        GEO_TARGETS_CRITERIA_ONLY_ALLOWED_IN_RULE_BASED_AUDIENCE
      </td>

      <td>
        when geo targets are passed for audiences other than rule based
      </td>
    </tr>

    <tr>
      <td>
        INCLUDE_AND_EXCLUDE_BROWSE_CRITERIA_CANNOT_BE_SAME
      </td>

      <td>
        when include and exclude browse criteria is same
      </td>
    </tr>

    <tr>
      <td>
        INCLUDE_AND_EXCLUDE_PURCHASE_CRITERIA_CANNOT_BE_SAME
      </td>

      <td>
        when include and exclude purchase criteria is same
      </td>
    </tr>

    <tr>
      <td>
        INCLUDE_SHOULD_NOT_BE_EMPTY_IN_ADVANCED_CRITERIA


      </td>

      <td>
        Include should not be empty in Advanced criteria
      </td>
    </tr>

    <tr>
      <td>
        INCLUSIONS_AND_EXCLUSIONS_ONLY_ALLOWED_IN_RULE_BASED_AUDIENCE
      </td>

      <td>
        when inclusions and exclusions are passed for audiences other than rule based
      </td>
    </tr>

    <tr>
      <td>
        INCOME_VALUES_NOT_IN_CORRECT_ORDER
      </td>

      <td>
        Income values are not in correct order in Rule Based criteria
      </td>
    </tr>

    <tr>
      <td>
        INVALID_ACTIVITY_PLATFORM
      </td>

      <td>
        when invalid activity platform in provided in rule based audience
      </td>
    </tr>

    <tr>
      <td>
        INVALID_ACTIVITY_TYPE
      </td>

      <td>
        when invalid activity type in provided in rule based audien
      </td>
    </tr>

    <tr>
      <td>
        INVALID_AD_GROUP_ID
      </td>

      <td>
        The provided entityId (lineItemId) is invalid
      </td>
    </tr>

    <tr>
      <td>
        INVALID_AUDIENCE_DEFINITION
      </td>

      <td>
        when invalid audience definition is passed
      </td>
    </tr>

    <tr>
      <td>
        INVALID_AUDIENCE_FREQUENCY
      </td>

      <td>
        when invalid audience frequency is provided
      </td>
    </tr>

    <tr>
      <td>
        INVALID_AUDIENCE_OBJECTIVE
      </td>

      <td>
        when invalid audience objective in provided
      </td>
    </tr>

    <tr>
      <td>
        INVALID_AUDIENCE_STATUS
      </td>

      <td>
        when invalid audience status is provided in filter\[status]
      </td>
    </tr>

    <tr>
      <td>
        INVALID_AUDIENCE_STRATEGY
      </td>

      <td>
        when invalid strategy is passed in item propensity audience request 
      </td>
    </tr>

    <tr>
      <td>
        INVALID_AUDIENCE_TAXONOMY
      </td>

      <td>
        when invalid audience taxonomy is provided. 

        The level system ranges from 1 to 3, with at least one level required, and must always start from level 1; levels 2 and 3 can only be created in sequential order following level 1.<br />For brand affinity audience, it is mandatory to provide all 3 levels.
      </td>
    </tr>

    <tr>
      <td>
        INVALID_BRAND_AFFINITY_TYPE
      </td>

      <td>
        when invalid brand affinity type is provided
      </td>
    </tr>

    <tr>
      <td>
        INVALID_BRAND_NAME_OR_ADVERTISER_DOES_NOT_HAVE_ACCESS_TO_BRAND
      </td>

      <td>
        when invalid brand name is provided or the provided advertise id does not have access to that particular brand
      </td>
    </tr>

    <tr>
      <td>
        INVALID_CONVERSION_EVENT
      </td>

      <td>
        One or more values in \`events\` are not valid; must be one of the supported ConversionEvent enum values
      </td>
    </tr>

    <tr>
      <td>
        INVALID_CONVERSION_FREQUENCY
      </td>

      <td>
        frequency must be between 1 and 5 (inclusive)
      </td>
    </tr>

    <tr>
      <td>
        INVALID_END_OFFSET_DAYS
      </td>

      <td>
        when invalid end offset days are provided
      </td>
    </tr>

    <tr>
      <td>
        INVALID_ENTITY_TYPE
      </td>

      <td>
        entityType must be one of: CAMPAIGN, AD_GROUP
      </td>
    </tr>

    <tr>
      <td>
        INVALID_EVENT_TYPE
      </td>

      <td>
        eventType must be one of: IMPRESSIONS, CLICKS
      </td>
    </tr>

    <tr>
      <td>
        INVALID_GENDER
      </td>

      <td>
        when invalid gender is passed, allowed values are M and F
      </td>
    </tr>

    <tr>
      <td>
        INVALID_PLATFORM
      </td>

      <td>
        when invalid platform is passed in rule based audience
      </td>
    </tr>

    <tr>
      <td>
        INVALID_PURCHASE_CHANNEL
      </td>

      <td>
        when invalid channel in provided in rule based audience
      </td>
    </tr>

    <tr>
      <td>
        INVALID_PURCHASE_PERCENTILE
      </td>

      <td>
        when invalid percentile is provided
      </td>
    </tr>

    <tr>
      <td>
        INVALID_SEED_AUDIENCE_ID
      </td>

      <td>
        when provided seed audience id does not exist
      </td>
    </tr>

    <tr>
      <td>
        INVALID_SIZE_FOR_SEED_AUDIENCE_ID
      </td>

      <td>
        when size of proivded seed audience id is less than 50k
      </td>
    </tr>

    <tr>
      <td>
        INVALID_START_OFFSET_DAYS
      </td>

      <td>
        when invalid start offset days are provided
      </td>
    </tr>

    <tr>
      <td>
        INVALID_STATE_OF_SEED_AUDIENCE_ID
      </td>

      <td>
        Seed Audience Id provided in request is not in a valid state
      </td>
    </tr>

    <tr>
      <td>
        INVALID_TAXONOMIES_OR_TAXONOMIES_DO_NOT_BELONG_TO_BRAND
      </td>

      <td>
        when invalid taxonomies are provided or the taxonomies do not belong to the brand
      </td>
    </tr>

    <tr>
      <td>
        ITEMSET_ID_DOES_NOT_EXIST_OR_NOT_ACCESSIBLE
      </td>

      <td>
        Item set id provided in audience definition does not exist or the advertiser does not have access
      </td>
    </tr>

    <tr>
      <td>
        ITEMSET_IDS_AND_TAXONOMIES_NOT_ALLOWED_TOGETHER
      </td>

      <td>
        when itemset ids and taxonomies are both passed in item propensity audience request
      </td>
    </tr>

    <tr>
      <td>
        ITEMSET_NOT_IN_BUILT_STATUS
      </td>

      <td>
        when itemset passed for audience estimate is not in built state
      </td>
    </tr>

    <tr>
      <td>
         LOOK_ALIKE_CRITERIA_MUST_BE_PROVIDED
      </td>

      <td>
        when lookalike criteria is missing for lookalike audience
      </td>
    </tr>

    <tr>
      <td>
        LOOK_ALIKE_CRITERIA_NOT_ALLOWED_FOR_BRAND_AFFINITY_AUDIENCE
      </td>

      <td>
        when lookalike criteria provided for brand affinity audience
      </td>
    </tr>

    <tr>
      <td>
        LOOK_ALIKE_CRITERIA_NOT_ALLOWED_FOR_ITEM_PROPENSITY_AUDIENCE


      </td>

      <td>
        when lookalike criteria provided in item propensity audience
      </td>
    </tr>

    <tr>
      <td>
        LOOK_ALIKE_CRITERIA_ONLY_ALLOWED_IN_LOOK_ALIKE_AUDIENCE
      </td>

      <td>
        when lookalike criteria is passed for audiences other than lookalike
      </td>
    </tr>

    <tr>
      <td>
        MEASUREMENT_ITEMSET_IDS_NOT_SUPPORTED
      </td>

      <td>
        when provided itemset id is a measurement itemset id
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_ATTRIBUTE
      </td>

      <td>
        when attribute field is missing in the request body
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_AUDIENCE_DEFINITION
      </td>

      <td>
        when audience definition field is missing in the request body
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_AUDIENCE_ID
      </td>

      <td>
        when audience id field is missing in the patch request body
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_AUDIENCE_OBJECTIVE
      </td>

      <td>
        when audience objective field is missing in the request body
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_AUDIENCE_TYPE
      </td>

      <td>
        when audience type field is missing in the request body
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_CONVERSION_EVENTS
      </td>

      <td>
        \`events\` field is required in conversionCriteria but was not provided
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_ENTITY_ID
      </td>

      <td>
        entityId is required inside entityRef but was not provided
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_ENTITY_REF
      </td>

      <td>
        entityRef is required in adExposureCriteria but was not provided
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_ENTITY_TYPE
      </td>

      <td>
        entityType is required inside entityRef but was not provided
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_EVENT_TYPE
      </td>

      <td>
        eventType is required in adExposureCriteria but was not provided
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_NAME
      </td>

      <td>
        when name field is missing in the request body
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_SEED_AUDIENCE_ID
      </td>

      <td>
        when seed audience id field is missing in lookalike audience request
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FIELD_USER_ACTIVITY_FREQUENCY
      </td>

      <td>
        when user activity frequency in not provided in browse criteria
      </td>
    </tr>

    <tr>
      <td>
        MISSING_FREQUENCY
      </td>

      <td>
        Frequency field is missing from Rule Based criteria
      </td>
    </tr>

    <tr>
      <td>
        MISSING_ITEMSETS_IN_CRITERIA
      </td>

      <td>
        Missing Itemsets in audience definition
      </td>
    </tr>

    <tr>
      <td>
        MISSING_OR_NULL_FREQUENCY_MIN_VALUE_FOR_RULE_BASED_CRITERIA
      </td>

      <td>
        Min value of Frequency field is missing from Rule Based criteria
      </td>
    </tr>

    <tr>
      <td>
        MISSING_START_OFFSET_DAYS
      </td>

      <td>
        Missing start offset dates in Rule Based Criteria
      </td>
    </tr>

    <tr>
      <td>
        NAME_LIMIT_EXCEEDED
      </td>

      <td>
        when provided name exceeds 120 chars
      </td>
    </tr>

    <tr>
      <td>
        _NO_RECORD_FOUND_
      </td>

      <td>
        when no records are present for some input
      </td>
    </tr>

    <tr>
      <td>
        OBJECTIVE_TEXT_LIMIT_EXCEEDED
      </td>

      <td>
        when objective text provided exceeds 120 chars
      </td>
    </tr>

    <tr>
      <td>
        OBJECTIVES_ARE_NOT_SUPPORTED_IN_ADVANCED_TARGETING
      </td>

      <td>
        Objectives are not supported in Advanced Audience Request
      </td>
    </tr>

    <tr>
      <td>
        ONE_OF_AUDIENCE_ID_OR_AUDIENCE_DEFINITION_IS_REQUIRED
      </td>

      <td>
        Either of the audience id or audience definition is required for Estimate api
      </td>
    </tr>

    <tr>
      <td>
        ONLY_CATEGORY_AND_CUSTOM_ITEMSETS_ALLOWED
      </td>

      <td>
        when category or custom itemset ids are not provided for item propensity audience
      </td>
    </tr>

    <tr>
      <td>
        ONLY_ONE_OF_AUDIENCE_ID_OR_AUDIENCE_DEFINITION_ARE_ALLOWED
      </td>

      <td>
        Only one of the audience id or audience definition is required for Estimate api
      </td>
    </tr>

    <tr>
      <td>
        ONLY_RULE_BASED_OR_ITEM_PROPENSITY_OR_LOOKALIKE_AUDIENCE_ALLOWED_AS_SEED_AUDIENCE_ID
      </td>

      <td>
        when seed audience id provided is not of rule based or item propensity or lookalike audience
      </td>
    </tr>

    <tr>
      <td>
        PROPENSITY_CRITERIA_MUST_BE_PROVIDED
      </td>

      <td>
        when propensity criteria in not provided for item propensity audience
      </td>
    </tr>

    <tr>
      <td>
        PROPENSITY_CRITERIA_NOT_ALLOWED_FOR_BRAND_AFFINITY_AUDIENCE
      </td>

      <td>
        when propensity criteria provided for brand affinity audience
      </td>
    </tr>

    <tr>
      <td>
        PROPENSITY_CRITERIA_NOT_ALLOWED_FOR_LOOK_ALIKE_AUDIENCE


      </td>

      <td>
        when propensity criteria provided in lookalike audience
      </td>
    </tr>

    <tr>
      <td>
        PROPENSITY_CRITERIA_ONLY_ALLOWED_IN_PROPENSITY_AUDIENCE
      </td>

      <td>
        when propensity criteria is passed for audiences other than item propensity
      </td>
    </tr>

    <tr>
      <td>
        PROVIDE_DATE_RANGE_OR_START_OFFSET_DAYS_FOR_PURCHASE_CRITERIA
      </td>

      <td>
        Date Range or Start Offset Date is not provided for Purchase Criteria
      </td>
    </tr>

    <tr>
      <td>
        PROVIDE_EITHER_CATEGORY_OR_ITEMSET_ID
      </td>

      <td>
        when none of itemset ids or categories are provided in item propensity audience
      </td>
    </tr>

    <tr>
      <td>
        PROVIDE_EITHER_FREQUENCY_OR_PERCENTILE
      </td>

      <td>
        when none of frequency or percentile are provided in rule based request
      </td>
    </tr>

    <tr>
      <td>
        PROVIDE_EITHER_OFFSET_OR_DATE_RANGE
      </td>

      <td>
        when both offset days and offset date are provided or none provided
      </td>
    </tr>

    <tr>
      <td>
        SAME_AUDIENCE_ID_NOT_ALLOWED_MORE_THAN_ONCE_IN_DEFINITION
      </td>

      <td>
        Same audience id can't be used within the advanced criteria
      </td>
    </tr>

    <tr>
      <td>
        SEED_AUDIENCE_ID_EXPIRED_OR_NOT_BUILT
      </td>

      <td>
        when seed audience id is expired or not in built state
      </td>
    </tr>

    <tr>
      <td>
        SEED_AUDIENCE_ID_NOT_FOUND_FOR_REQUESTED_ADVERTISER
      </td>

      <td>
        Seed Audience Id provided in advanced criteria does not exist for the advertiser
      </td>
    </tr>

    <tr>
      <td>
        SEED_AUDIENCE_NOT_READY_TO_ESTIMATE
      </td>

      <td>
        Seed Audience Id provided is not ready to estimate for size
      </td>
    </tr>

    <tr>
      <td>
        START_DATE_MUST_BE_WITHIN_LAST_1_YEAR
      </td>

      <td>
        The start date must fall within the last 1 year from today
      </td>
    </tr>

    <tr>
      <td>
        START_DATE_MUST_BE_WITHIN_LAST_5_YEARS
      </td>

      <td>
        when start date is older than last 5 years
      </td>
    </tr>

    <tr>
      <td>
        START_OFFSET_DAYS_MISSING_FOR_BROWSE_CRITERIA
      </td>

      <td>
        when start offset days is not provided in browse criteria of rule based audience
      </td>
    </tr>

    <tr>
      <td>
        UNSUPPORTED_CRITERIA_FOR_ESTIMATION
      </td>

      <td>
        Audience Criteria provided for estimation api is not supported
      </td>
    </tr>

    <tr>
      <td>
        UNSUPPORTED_TOP_DECILE
      </td>

      <td>
        Value of top decile provided is not supported
      </td>
    </tr>
  </tbody>
</Table>


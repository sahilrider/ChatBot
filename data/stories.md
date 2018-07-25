## start
* greet
   -utter_greet
> pre_login
   - utter_ask_login_for_services
   - utter_optional
> asked_login

## optional1
> asked_login
* what_services
   - utter_bot_services
> pre_login

## optional2
> asked_login
* no_account
   - utter_account_help
> pre_login

## optional3
> asked_login
* creators
   - utter_bot_details
> pre_login

## affirm_login
> asked_login
* affirm_log
   - utter_login
* input_loginid
   - utter_loginsuccess
   - utter_askservice
> logged_in 

## deny_login
> asked_login
* deny_log
   - utter_extra
> asked_offers

## extra
> asked_offers
* affirm
   - utter_offers1
   - utter_offers2
> offerext

## quit
> asked_offers
* deny
   - utter_goodbye
> pre_login

## balance_success
> logged_in
* balance
   - utter_balance
   - utter_anythingelse
> cont_service

## transfer_success
> logged_in
* transfer
   - utter_askAccNo
* input_receiveracc
   - utter_askAmt
* input_transferamt
   - utter_success
   - utter_anythingelse
> cont_service

## continue_service_affirm
> cont_service
* affirm
   - utter_askservice
> logged_in

## continue_service_deny
> cont_service
* deny
   - utter_goodbye_logout
> pre_login

## continue_affirm_ext
> service_continue_ext
* affirm
> pre_login

## continue_deny_ext
> service_continue_ext
* deny
   - utter_goodbye
> pre_login

## offers_ext_loan
> offerext
* describe_loans
   - utter_loanDesc
   - utter_askregister
> register_ask_ext

## offers_affirm_ext
> register_ask_ext
* affirm
   - utter_askmail
* input_email
   - utter_confirmregister
   - utter_anythingelse_ext
> service_continue_ext

## offers_deny_ext
> register_ask_ext
* deny
   - utter_anythingelse_ext
> service_continue_ext

## offers_ext_credit
> offerext
* describe_credit
   - utter_creditCardDesc
   - utter_askregister
> register_ask_ext

## offers_ext_debit
> offerext
* describe_debit
   - utter_debitCardDesc
   - utter_askregister
> register_ask_ext

##show_offers
> logged_in
* offers
   - utter_offers1
   - utter_offers2
> offer

## show_offers_loan
> offer
* describe_loans
   - utter_loanDesc
   - utter_askregister
> asked_offer_register

## show_offers_deny
> asked_offer_register
* deny
   - utter_anythingelse
> cont_service

## show_offers_affirm
> asked_offer_register
* affirm
   - utter_confirmregister
   - utter_anythingelse
> cont_service

## show_offers_credit
> offer
* describe_credit
   - utter_creditCardDesc
   - utter_askregister
> asked_offer_register

## show_offers_debit
> offer
* describe_debit
   - utter_debitCardDesc
   - utter_askregister
> asked_offer_register

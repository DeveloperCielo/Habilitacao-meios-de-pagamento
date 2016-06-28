---
title: Procedures for enable Payment methods

toc_footers:
  - <a href='/Checkout-Cielo/english.html'>Manual Checkout Cielo</a>
  - <a href='/Checkout-FAQ/'>Perguntas Frequêntes</a>

search: true
---

# Procedures for enable Payment methods

## About this Manual

The manual aims to guide the retailer in hiring the BOLETO and ONLINE DEBT payment method available on CIELO CHECKOUT.

## Changelog

* **1.4** - 08/06/2015
    * Inclusion of BOLETO SPS Bradesco.
* **1.3** - 03/24/2015
    * Inclusion of signature field in Online Debit Bradesco.
* **1.2** - 01/09/2015
    * Review of items requested to generate boleto
    * Upgrade of integrated solution name becomes Cielo Checkout
* **1.1** - 08/20/2014
    * Update of Bradesco Boleto data (IP) and URL debit (BB)
* **1.0** - 08/07/2014
    * Initial version

## Boleto

Using CIELO Checkout, the retailer can accept Boleto issued by Bradesco and Banco do Brasil banks.

## Online debit (Electronic Transfer)

In this payment method the data is entered directly in the Bank's environment, all banks have a policy to redirect these transactions to their environment, making the transaction more safe.

# Boleto qualification

## Bradesco

The criteria for using Boleto Bradesco Eletronic Com. are:

* Be Corporate accountholder Bradesco;
* Contact Bradesco account manager to sign specific Electronic Commerce contract.

To order/configure Boleto Bradesco, you will need:

1. Contact the bank/branch and make the request for boleto with registration wallet 26. This step involves contract signature with the Bank.
2. Receive an e-mail from the Bank (Scopus Kit) with manager URL, e-mail, login and password to access Bradesco environment.You must access Bradesco environment using manager URL. See examples sent in email (Scopus Kit)
    * **Manager URL** - (https://meiosdepagamentobradesco.com.br/gerenciador/login.jsp)
    * **E-mail Login**
    * **Password**

To configure Boleto:

**1.** At Bradesco environment, access the tabs SETTINGS > PAYMENT'S METHOD > BOLETO and fill in the following data:

* **Enable Boleto "sentence"**: Inactive
* **Enable Boleto "reference"**: Active
* **Presenting Agency and Account**: Inactive
* **Expiration date**: 5 days

![Boleto Bradesco](/images/boleto-bradesco-passo-2.png)

<aside class="notice"><strong>Note:</strong> The expiration date must be in the same Cielo Checkout.</aside>

* **Notification URL**: https://www.pagador.com.br/post/BoletoBradescoSps/ReceivePost
* In the **Security Key field** click on **"Generate security key"**
* **Store IP address (numeric)**
* For the response **URL fields, URL of failure and URL of redirection**, insert the following link: https://www.pagador.com.br/post/BoletoBradescoSps/ReceivePost

![Boleto Bradesco](/images/boleto-bradesco-passo-3.png)

**2.** In each three parameters following, complete with the Communication Parameter below:

* **Notification Parameter**:
    * `numOrder=[%lid_m%]&merchantid=[%merchantid%]&cod=[%errorcod%]&cctype=[%cctype%]&ccname=[%ccname%]&ccemail=[%ccemail%]&numparc=[%numparc%]&valparc=[%valparc%]&valtotal=[%valtotal%]&prazo=[%prazo%]&comb=[%comb%]&assinatura=[%assinatura%]&`
* **Confirmation Parameter**:
    * `numOrder=[%lid_m%]&merchantid=[%merchantid%]&cod=[%errorcod%]&cctype=[%cctype%]&ccname=[%ccname%]&ccemail=[%ccemail%]&numparc=[%numparc%]&valparc=[%valparc%]&valtotal=[%valtotal%]&prazo=[%prazo%]&comb=[%comb%]&assinatura=[%assinatura%]&`
* **Fault Parameters**:
    * `numOrder=[%lid_m%]&merchantid=[%merchantid%]&cod=[%errorcod%]&cctype=[%cctype%]&ccname=[%ccname%]&ccemail=[%ccemail%]&numparc=[%numparc%]&valparc=[%valparc%]&valtotal=[%valtotal%]&prazo=[%prazo%]&comb=[%comb%]&assinatura=[%assinatura%]&`
* **Parameter Communication**:
    * `numOrder=[%lid_m%]&merchantid=[%merchantid%]&cod=[%errorcod%]&cctype=[%cctype%]&ccname=[%ccname%]&ccemail=[%ccemail%]&numparc=[%numparc%]&valparc=[%valparc%]&valtotal=[%valtotal%]&prazo=[%prazo%]&comb=[%comb%]&assinatura=[%assinatura%]&`

![Boleto Bradesco](/images/boleto-bradesco-passo-4.png)

<aside class="notice"><strong>Note</strong>: There can be no spaces or text breaks in exposed above parameters.</aside>

**3.** Click at the buttom **"Save all settings made"**

### After complete this step, you must:

**1.** Send an email to Cielo e-Commerce [cieloecommerce@cielo.com.br](mailto:cieloecommerce@cielo.com.br) with the following data:

* **Agency:** 0000
* **Account:** 0000000 (7 dígitos sem o dígito verificador, mantendo os zeros à esquerda conforme exemplo: 0001111
* **Agreement:** 000000
* **Wallet:** 26 - WITH REGISTRATION
* **Expiry date** (measured in days):
* **Conciliation** (Bradesco Membership):
    * Reconciliation Example: 004601478
* **Security Key** (Bradesco):
    * Example of Security Key: `ZDE50B48D41D59BDD1562CC2A48546454ZC149308CBD283E0E49210C57958A6A38A068A3ZZA8B075095A1B9E1DEAZB64BF1682C5610ZC8285DC8630FA6E300FA00B9D43054C84ACA958ZCFB435CF5A27ZC440637777EBAFEED1BCZDCA82D5778B266B3BB4E90774302D56A0C7EDZZ1A532A51F7A889DA83AEFA08CA4E91A08Z2`

<aside class="notice"><strong>Note</strong>: Membership Bradesco is located on top of the web manager.</aside>

![Boleto Bradesco](/images/boleto-bradesco-passo-5.png)

**2.** Cielo e-commerce will confirm, within 3 days, the inclusion of boleto as payment method in your online store.

## Banco do Brasil

The criteria to enable Banco do Brasil Boleto are:

* Be accountholder of Banco do Brasil (Corporative Register);

To request Banco do Brasil Boleto you will need:

1. Contact the bank/branch and make the boleto request unregistered wallet 18. This step involves signing a contract with the Bank
2. Send an email to Cielo e-Commerce cieloecommerce@cielo.com.br with the following data:
    * **Agency**: 0000
    * **Current Account**: 00000-0
    * **Agreement**: 0000000
    * **Expiry date** (measured in days):
    * **Wallet**: 18 - NO REGISTRATION

<aside class="notice">Boleto validity - If the boleto expires on a non-working day, like Saturday, it will be valid until the next business day</aside>

# Enable Online Debit

## Bradesco

1. Ask your manager to release Bradesco's online debt (Bradesco SPS). The affiliation will be sent by Bradesco using the pattern:
    * **Agreement approval**: 101xx1
    * **Login**: dm_cm132
    * **Password**: 12345678
    * **Signature**: 8EA7657E-6373-667D-0229-A82E842A3A1A
2. On receiving this information, the merchant must request an oauthorization of the payment method for Cielo.
3. Sign up in MUP test (Bradesco system, the e-mail with Bradesco's data will include the URL to access). Register the information below:
    * **Store's IP address**: 209.134.48.121
    * In "Purchase confirmation page" and "Error Page at payment": https://www.pagador.com.br/pagador/recebe.asp
    * In "URL for reporting for Bradesco Cards": https://www.pagador.com.br/pagador/bradesco/setTransacao.asp
    * In The Fields "Post to be sent to the store in the notification", "Post to be sent to the store in order confirmation" and "Post to send to the store in the authorization failure":
        * **Add**: `numOrder=[%lid_m%]&merchantid=[%merchantid%]&cod=[%errorcod%]&cctype=[%cctype%]&ccname=[%ccname%]&ccemail=[%ccemail%]&numparc=[%numparc%]&valparc=[%valparc%]&valtotal=[%valtotal%]&prazo=[%prazo%]&tipopagto=[%tipopagto%]&assinatura=[%assinatura%]`
    * In "Incoming URL in the store": Website address
    * In "URL Store manager": https://www.pagador.com.br/admin/login.asp
    * The last option: Capture now (1001).
4. Send your email below to Scopus requesting approval/homologation
    * **To**: [homologacao@scopus.com.br](mailto:homologacao@scopus.com.br); [kit@scopus.com.br](mailto:kit@scopus.com.br)
    * **Subject**: Data of production environment Debit SPS
    * **Body of e-mail**:<br />Dear,<br /><br />Please release the customer below for production environment:<br /><br />Company Name: XXXXX<br />CNPJ: XXXX<br />Store Name: XXXXX<br />Store Number: XXXXX<br />Manager: XXXXX<br />Password: XXXXXXX<br />Store URL: https: //www.XXXXXXXXX<br />Payment methods to ratify: Debit Account
5. Receive production data:
    * Bradesco will send the membership using the pattern:
        * **Production Agreement**: 101xx1
        * **Login**: dm_cm132
        * **Password**: 12345678
        * **URL for testing**: http://mup.comercioeletronico.com.br/sepsManager/senha.asp?loja=XXXX
6. Sign up for MUP Production, the same information from step 3.
7. Ask Cielo to update the Agreement number for production number that has received in step 5.

## Banco do Brasil

Ask your bank manager to release the agreement of online debit via Internet (Banco do Brasil Electronic Commerce - BBPAG) and the registration of Communication URL with Cielo.

* **Communication URL**: https://www.pagador.com.br

The manager must register this URL at the time of release the agreement.

<aside class="warning">If you do not register it will not operate.</aside>

* **Example of agreement**: Agreement: 000000

# AISP Account Transactions

Paged list of transactions of a selected client account.

* **URL**

  `/my/accounts/{id}/transactions{?fromDate,toDate,currency,size,page,sort,order}`

* **Method:**
  
  `GET`
  
*  **URL Params**

   - **id** - API payment account identifier from the response to a query on the list of accounts.
   - **currency** - Required account currency for multi-currency accounts.
   - **fromDate** - Date and time of the start of required transaction history
   - **toDate** - Date and time of the end of required transaction history [inclusive]
   - **currency** - Required account currency for multi-currency accounts
   - **size** - Paging. Number of entries per page
   - **page** - Paging. Required page. + Default: 0
   - **sort** - A list of fields separated by comma for sorting, arranged according to the meaning
   - **order** - A list of arrangement methods (ASC, DESC) separated by comma. The order corresponds to the order of fields in the sort parameter.


* **Request**

  `/my/accounts/D2C8C1DCC51A3738538A40A4863CA288E0225E52/transactions`

  **Header:**
  ```http
  GET https://api.bank.cz/v1/my/accounts/D2C8C1DCC51A3738538A40A4863CA288E0225E52/transactions
  Content-Type: application/json
  X-Request-ID: 55d4fffc-2634-44d4-9f2b-3aa94fbd51a4
  Date: Wed, 6 Jan 2019 07:23:01 GMT
  User-Involved: false
  API-key: 00000000-1212-0f0f-a0a0-123456789abc
  TPP-Name: Google China
  Authorization: Bearer AbCdEf123456
  ```

  **Payload:**
  
  not defined

* **Success Response:**
  
  **Code:** 200 <br />
  **Header:**
  ```http
  HTTP/1.1 200 OK
  Content-Type: application/json
  X-Request-ID: 55d4fffc-2634-44d4-9f2b-3aa94fbd51a4
  ```

  **Payload: [200_response.json](200_response.json)**
  ```json
  {
   "pageNumber":0,
   "pageCount":2,
   "pageSize":100,
   "nextPage":1,
   "transactions":[
      {
         "entryReference":"RB-4567813",
         "amount":{
            "value":10000.00,
            "currency":"CZK"
         },
         "status":"BOOK",
         "creditDebitIndicator":"DBIT",
         "bookingDate":{
            "date":"2017-01-31T00:00:00.000+01"
         },
         "valueDate":{
            "date":"2017-01-31T00:00:00.000+01"
         },
         "bankTransactionCode":{
            "proprietary":{
               "code":1000010,
               "issuer":"CBA"
            }
         },
         "entryDetails":{
            "transactionDetails":{
               "amountDetails":{
                  "instructedAmount":{
                     "amount":{
                        "value":10000.00,
                        "currency":"CZK"
                     }
                  }
               },
               "relatedParties":{
                  "debtor":{
                     "name":"Novák Jan"
                  },
                  "debtorAccount":{
                     "identification":{
                        "iban":"CZ0827000000002108589434",
                        "other":{
                           "identification":"0000002108589434"
                        }
                     }
                  }
               },
               "relatedAgents":{
                  "debtorAgent":{
                     "financialInstitutionIdentification":{
                        "bic":"BACXCZPP",
                        "clearingSystemMemberIdentification":{
                           "memberIdentification":"2700"
                        }
                     }
                  }
               },
               "remittanceInformation":{
                  "unstructured":"``",
                  "structured":{
                     "creditorReferenceInformation":{
                        "reference":"VS:123456\",\"KS:456789\",\"SS:879213546"
                     }
                  }
               },
               "additionalTransactionInformation":"Domácí platba - S24/IB,záloha plyn Bohemia Energy"
            }
         }
      },
      {
         "amount":{
            "value":105.25,
            "currency":"CZK"
         },
         "status":"BOOK",
         "creditDebitIndicator":"DBIT",
         "bookingDate":{
            "date":"2016-09-05T00:00:00+01:00"
         },
         "valueDate":{
            "date":"2016-09-05T00:00:00+01:00"
         },
         "bankTransactionCode":{
            "proprietary":{
               "code":4000050,
               "issuer":"CBA"
            }
         },
         "entryDetails":{
            "transactionDetails":{
               "references":{
                  "chequeNumber":"xxxxxxxxxxxx1248"
               },
               "amountDetails":{
                  "instructedAmount":{
                     "amount":{
                        "value":10.00,
                        "currency":"GBP"
                     }
                  },
                  "counterValueAmount":{
                     "amount":{
                        "currency":"CZK",
                        "value":105.25
                     },
                     "currencyExchange":{
                        "sourceCurrency":"CZK",
                        "targetCurrency":"GBP",
                        "exchangeRate":10.525
                     }
                  }
               },
               "additionalTransactionInformation":"PLATBA KARTOU"
            }
         }
      },
      {
         "entryReference":"FC-4567513951",
         "amount":{
            "value":1844777.00,
            "currency":"CZK"
         },
         "status":"BOOK",
         "creditDebitIndicator":"CRDT",
         "bookingDate":{
            "date":"2017-01-31T00:00:00.000+01"
         },
         "valueDate":{
            "date":"2017-01-31T00:00:00.000+01"
         },
         "bankTransactionCode":{
            "proprietary":{
               "code":1000020,
               "issuer":"CBA"
            }
         },
         "entryDetails":{

         }
      },
      {
         "entryReference":"CDR-13457893331",
         "amount":{
            "value":2.00,
            "currency":"CZK"
         },
         "status":"BOOK",
         "creditDebitIndicator":"DBIT",
         "bookingDate":{
            "date":"2016-09-05T00:00:00+01:00"
         },
         "valueDate":{
            "date":"2016-09-05T00:00:00+01:00"
         },
         "bankTransactionCode":{
            "proprietary":{
               "code":4000010,
               "issuer":"CBA"
            }
         },
         "entryDetails":{
            "transactionDetails":{
               "amountDetails":{
                  "instructedAmount":{
                     "amount":{
                        "value":2.00,
                        "currency":"CZK"
                     }
                  }
               },
               "additionalTransactionInformation":"POPLATEK ZA ODCHOZÍ TRANSAKCÍ"
            }
         }
      },
      {
         "amount":{
            "value":122.22,
            "currency":"CZK"
         },
         "status":"BOOK",
         "creditDebitIndicator":"CRDT",
         "bookingDate":{
            "date":"2016-09-05T00:00:00+01:00"
         },
         "valueDate":{
            "date":"2016-09-05T00:00:00+01:00"
         },
         "bankTransactionCode":{
            "proprietary":{
               "code":9000020,
               "issuer":"CBA"
            }
         },
         "entryDetails":{
            "transactionDetails":{
               "amountDetails":{
                  "instructedAmount":{
                     "amount":{
                        "value":122.22,
                        "currency":"CZK"
                     }
                  }
               },
               "additionalTransactionInformation":"PŘIPSÁNÍ ÚROKU ZE ZUSTATKU"
            }
         }
      },
      {
         "entryReference":"FP-4156489123",
         "amount":{
            "value":23282.62,
            "currency":"CZK"
         },
         "status":"BOOK",
         "creditDebitIndicator":"CRDT",
         "bookingDate":{
            "date":"2017-01-31T00:00:00.000+01"
         },
         "valueDate":{
            "date":"2017-01-31T00:00:00.000+01"
         },
         "bankTransactionCode":{
            "proprietary":{
               "code":1000040,
               "issuer":"CBA"
            }
         },
         "entryDetails":{
            "transactionDetails":{
               "references":{
                  "endToEndIdentification":"VS0250117002/SS0000000000/KS0000"
               },
               "amountDetails":{
                  "instructedAmount":{
                     "amount":{
                        "value":23282.62,
                        "currency":"CZK"
                     }
                  },
                  "counterValueAmount":{
                     "amount":{
                        "currency":"EUR",
                        "value":86200.00
                     },
                     "currencyExchange":{
                        "sourceCurrency":"EUR",
                        "targetCurrency":"CZK",
                        "exchangeRate":27.01
                     }
                  }
               },
               "relatedParties":{
                  "debtor":{
                     "name":"RENWORTH s.r.o",
                     "identification":{
                        "organisationIdentification":{
                           "other":{
                              "identification":"48135283",
                              "schemeName":{
                                 "code":"1.2.203.48135283",
                                 "proprietary":"RENWORTH s.r.o"
                              }
                           }
                        }
                     }
                  },
                  "debtorAccount":{
                     "identification":{
                        "iban":"CZ1308001800640033122856"
                     }
                  }
               },
               "relatedAgents":{
                  "debtorAgent":{
                     "financialInstitutionIdentification":{
                        "bic":"GIBACZPXXXX"
                     }
                  }
               },
               "purpose":{
                  "proprietary":"PLATBA ZA SLUŽBY"
               },
               "remittanceInformation":{
                  "structured":{
                     "creditorReferenceInformation":{
                        "reference":"VS:0250117002"
                     }
                  }
               },
               "additionalTransactionInformation":"8201701069595 BIC: GIBACZPXXXX; #71A# SHA ZALOHA DLE SMLOUVY O DODAVKACH,zaloha dle smlouvy o dodavkach c. 45678/2017,VS0250117002/SS0000000000/KS0000SEPA převod"
            }
         }
      },
      {
         "amount":{
            "value":105.00,
            "currency":"CZK"
         },
         "status":"BOOK",
         "creditDebitIndicator":"CRDT",
         "bookingDate":{
            "date":"2016-09-05T00:00:00+01:00"
         },
         "valueDate":{
            "date":"2016-09-05T00:00:00+01:00"
         },
         "bankTransactionCode":{
            "proprietary":{
               "code":2000010,
               "issuer":"CBA"
            }
         }
      }
   ]
  }
  ```
 
* **Error Responses:**

  **Code:** 404 Not Found <br />
  **Header:**
  ```http
  HTTP/1.1 404 Not Found
  Content-Type: application/json
  X-Request-ID: 55d4fffc-2634-44d4-9f2b-3aa94fbd51a4
  ```
  
  **Payload: [404_response.json](404_response.json)**
  ```json
  {
   "errors":[
      {
         "error":"ID_NOT_FOUND"
      }
   ]
  }
  ```
  
  OR
  
  **Code:** 400 Bad Request <br />
  **Header:**
  ```http
  HTTP/1.1 400 Bad Request
  Content-Type: application/json
  X-Request-ID: 55d4fffc-2634-44d4-9f2b-3aa94fbd51a4
  ```
  
  **Payload: [400_response.json](400_response.json)**
  ```json
  {
   "errors":[
      {
         "error":"AM03",
         "scope":"currency"
      },
      {
         "error":"DT01",
         "parameters":{
            "DATE":"DATE_TO_OLD"
         },
         "scope":"fromDate"
      },
      {
         "error":"DT01",
         "parameters":{
            "DATE":"DATE_IN_FUTURE"
         },
         "scope":"toDate"
      }
   ]
  }
  ```
  


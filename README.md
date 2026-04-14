# ap3-protocol
An open protocol for privacy-preserving computation in agentic commerce. Agents compute on data. They never read it.

# **AP3 - Privacy Protocol for Agentic Commerce**   

AP3 is a privacy protocol that is built on top of the A2A (Agent to Agent) communication protocols, and alongside payment protocols such as AP2, ACP and so on. A2A defines how agents communicate. AP2 / ACP and other payment protocols define how agents pay. AP3 defines what agents are allowed to see. AP3 is an open protocol for privacy-preserving computation in agentic commerce. It enables AI agents to negotiate, verify, and transact on behalf of users and organisations without the counterparty agent ever accessing the underlying data. 

# **What is the problem that AP3 solves?**

When two agents exchange sensitive data inside an A2A message today, the receiving agent sees the raw data. The agentic commerce defaults to full data exposure at the agent interaction layer. Some examples: An enterprise's procurement agent reveals its actual budget to negotiate with a supplier. A borrower's agent transmits full bank statements to a lender. A user's agent sends complete identity documents to a verification service. The agents can read, store, and use sensitive data, beyond the agreed purpose. 

A2A just governs how agents communicate. They don’t govern how the data is processed or what is shared. There is no cryptographic guarantee of non-exposure. It cannot promise: 

1. That the agent did not read your private data
2. That LSP did not store your private data
3. That HDFC did not share your private data with a third party
4. That the user agent did not send more data than necessary
5. That either party behaved honestly with what they received

Enter AP3. When sensitive data is exchanged inside an A2A message — income, identity, budget, pricing - AP3 intercepts the payload, runs the required computation across encrypted inputs, and returns a verifiable result to the receiving agent. The receiving agent gets what it needs to make a decision. It never gets the data itself.

## **AP3 can promise:** 

1. No data is seen, read or stored 
2. Defines how sensitive data is being used 
3. Defines how sensitive data is encrypted and computed upon so no one sees the raw input
4. AP3 fits in specifically in the message layer in the A2A protocols, when private data is being exchanged

AP3 produces a cryptographic proof in place of raw data, and provides an audit trail of cryptographically signed records confirming that no data was exposed, that every computation was authorised by the data owner, and that the result is accurate and verifiable.
AP3 makes acting on data and reading data two different things.                                                                                                                                              
# **How AP3 Works**                                                                                                                                                                                               
AP3 sits in the A2A message layer. Not every message requires AP3 - only messages carrying sensitive data. The developer defines which fields trigger AP3 (income, identity, budget, age, pricing). When those fields are present, AP3:                                                                                                                                                                             
1. Intercepts the sensitive payload before it reaches the counterparty agent                                                                  2. Runs the required computation across encrypted, distributed inputs using Multi-Party Computation (MPC)
3. Returns a verifiable inference token to the receiving agent — the answer to the question, not the underlying data
4. If the out or the natural next step is a payment, it produces an output that is compatible with AP2 and other payment protocols so that the agent can proceed with payment
5. Produces a cryptographic audit trail confirming no raw data was exposed and the computation matched the user's consent                                                                                    
# **Where AP3 Fits in the Agentic Stack**                                                                                                       

A2A - Agent communication protocol- (how agents talk)                                                                                         AP3 - Privacy protocol - (what agents are allowed to see)  ← this project
AP2 - Payment protocol - (how agents pay)

AP3 and AP2 are sequenced, not competing. AP3 protects the data being negotiated. AP2 executes the transaction on the agreed terms. The AP3 output artifact feeds directly into the AP2 payment flow. And AP3 will be built payment protocol agnostic, AP2 is the just first protocol AP3 will support

# **Real World Use Case Examples** 

## Persona 1: Non-entitled entity - computation on data you cannot access 

1. Visa processing: "Financially credible to travel: "yes" — without seeing bank statements
2. Tenant screening: "Can afford rent: "yes" — without seeing full financials
3. Employer income verification: "Income matches claim: yes" — without accessing bank data
4. Fintech risk profiling: Creditworthiness signal — without compelling KYC data access                                                                                                                       
                                                            
## Persona 2: Mutual confidentiality - negotiation on data you cannot afford to reveal                                                                                                                                     
1. Manufacturer and supplier negotiation: Neither reveals cost floor or budget ceiling, but both learn if a deal is possible
2. Route matching: Truckers match space capacity on pre-existing routes without revealing entire capacity and schedules. Real world problem statement we are working on today
3. Joint procurement: Two companies co-buy for volume discounts without revealing individual volumes                                                                                                                                                                                 
# **Key Properties**                          
                                                                                                                                              1. No raw data exposure — The receiving agent never sees the underlying data. AP3 returns an output, which can be binary in nature (yes / no), some price (if price negotiation), or some terms (loan terms if BNPL use case)                                                           2. Cryptographic audit trail — Every computation produces a signed record confirming what was computed, by whom, under what consent, and what was returned.
3. No changes to existing infrastructure — AP3 works with existing A2A-compliant agents via SDK integration. It just requires the developer to integrate with the AP3 SDK at the time of agent set up, update it on the Agent Card, and create rules on what constitutes as "sensitive" data in order to invoke AP3
4. Interoperable — Compatible with any A2A-compliant agent and integrates with AP2-enabled payment flows. Built to be payment protocol and agent platform agnostic. 

# **Technology**                                                

1. Multi-Party Computation (MPC) — Computation runs across distributed nodes, each holding only a fragment of the data. No single node ever holds or sees the complete input.
2. Zero Knowledge Proofs (ZKP) — Proves the output of computation is correct without revealing the inputs to the verifier.

# **Project Status**                                            
                                                                                                                                            AP3 is at specification stage. XX

## **SDK implementations are in development**
                                                                                                                                            
ap3-sdk-python — coming soon 
ap3-sdk-js — coming soon  

# **License**                                                                                                                                 

AP3 is licensed under the ./LICENSE.                                                                                                          

**Contact**  

For questions about the AP3 protocol: open an issue in this repository.
For security vulnerabilities: see ./SECURITY.md.
For enterprise integration and support: contact Silence Laboratories at info@silencelabratories.com

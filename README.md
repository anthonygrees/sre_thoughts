# SRE - Thoughts, Best Practices & Frameworks
 
Due to my background in automation at large scale, I'm often asked for advice on SRE practices.  Fortunately I worked with some of the best SRE's in the business, including [@NathenHarvey](https://github.com/nathenharvey) - Developer Advocate for Google Cloud Platform.  
  
  
### 1. The First Question 
  
When I meet a customer or colleague who askes about SRE, I always ask these initial questions:  
- How did you find out about your last outage ?  
- What was the impact to your customers ?  
- How did your organisation respond ?  
  
### 2. What is SRE
  
Site Reliability Engineering (SRE) is a set of principles, practices, and organisational constructs that seek to balance the reliability of a service with the need to continually deliver new features.  

The REAL definition.  
Yes, it was created by Google.  SRE is what you get when you treat operations as a software problem.  Using code for availability, latency, performance and capacity.  
  
Some things to remember:  
1. The MOST important feature of any system is it’s reliability.  
2. Our monitoring does not only decide our reliability because our Users do.  
3. Reliability comes from great engineered Software, Operations and Business working `together`.  
  
### 3. SRE Measures
  
The 3 most important measures for an SRE.  

#### 3.1 SLI - Service Level Indicator
Metrics that describe users experience.  
- Response times  
- Ticket Queue monitoring  
- Net Promoter Score  
- Twitter sentiment  
- Reddit issues  
  
#### 3.2 SLO - Service Level Objective
Our target health  
- how good does our customer need it ?  

#### 3.3 SLA - Service Level Agreement
Contractable obligation  
- Penalties  
- Restore times  
  
  
We want to be asking ourselves:  
```bash
When do we need to make a system more reliable ?
```
  
### 4. SRE Framework - Error Budget
  
What is an `Error Budget` ???   
- Targeting less than 100% reliability means targeting more than 0% unreliability
- An acceptable rate or errors
- This is a budget that can be allocated
  
```bash
Eg.
SLO: 99.9%
Error budget: 100% - 99.9% = 0.1%
For a 1B query/month service - 1 million errors to “Spend” !
```
  
### 5. Implications of Error Budget (behaviours and rules)
  
What to do when you have budget to spend and what to do when your out of budget !  
  
#### 5.1 Prioritise Reliability  (when budget is exhausted)
- prioritise postmortem items
- Automate deployment pipelines
- Improve monitoring and observability
- Require SRE consultation
  
#### 5.2 Prioritise Velocity (When budget is available)
- Expected system changes
- Inevitable failure in hardware, networks, etc
- Planned downtime
- Risky experiments
  
### 6. Site Reliability Hierarchy - Monitoring 
This is the hierachy of SRE's as defined by Google.  
![Site Reliability Hierarchy](/images/dickersons-hierarchy-of-service-reliability.png)
  
### 7. Remember this about incidents
Firefighters say `We have never responded to an emergency` !  They practice to put out a fire on a burning house.  
SRE’s must practice to respond to incidents because outages WILL happen !  
  
As they say:  
```bash
An incident is an unplanned investment !
```
  
### 8. How do we learn from Incidents ?  
The `Framework` is as follows:  
```bash
Detect -> Investigate -> Mitigate -> Fix -> Learn
```

### 9. Resources
- Free books - https://sre.google/books/   
- Splunk SRE site - https://www.observability.splunk.com/en_us/infrastructure-monitoring/guide-to-sre-and-the-four-golden-signals-of-monitoring.html


### 10. Going Back to the Questions Above
So, what are the answers to my questions above ?  
  
- How did you find out about your last outage ?  
`It’s your SLI.` 
  
- What was the impact to your customers ?  
`It’s your SLO.` 
  
- How did your organisation respond ?  
`Error budget consequences.` 
  

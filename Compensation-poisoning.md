## Context and Some Related Concepts

Many actors take responsibility after hacks involving Twitter accounts, smart contracts, or platforms, and proceed to compensate affected users. However, the way eligibility for compensation is determined often contains flaws that attackers can exploit to make themselves appear as victims and qualify for payouts. We call this attack **compensation poisoning**.

The major flaw is **blind compensation**, which stipulates that any address that interacted with the contract within a time interval is considered a victim and is eligible for compensation.

Any compensation that is done blindly is vulnerable to **compensation poisoning**.

Awarding blind compensation to attackers creates **a double-profit incentive**, and it could inspire a new attack strategy where attackers deliberately target systems knowing they can profit both from the exploit and from the subsequent compensation payout.


 ## Case Study: Compensation for Victims of the BNB Chain Twitter Account Hack 

[BNB Chain Compensation Announcement](https://x.com/BNBCHAIN/status/1984143649584902620)

By analyzing the [compensation transaction](https://etherscan.io/tx/0xc4373bac712414b10c91ac5a95c096925f62b835f3b6893464df205cbe178e8a) 
posted by the BNB Chain account, we can infer the eligibility rules for 
compensation: any address that interacted with the contract within a time 
interval is considered a victim and is eligible for compensation. Thus, 
this is a blind compensation approach.

Now let's verify whether **this blind compensation awarded compensation to 
the attacker.**

We will analyze the address `0x622450202ccf63C5750c699b56543eE8fd8E3F5A`. 
Here are the two transactions that prove it was a victim of the attack: 
[Transaction 1](https://etherscan.io/tx/0x9183c1c42fa639d29ec342160310686f984815a85f68a41e270d6908707aadec) 
and [Transaction 2](https://etherscan.io/tx/0x9e23c2b164403c99090c0b32fdcd8343b5e86ba97efefa3aa97bcb9e6302bfa1).
And here we can find the [compensation for this address](https://etherscan.io/tx/0xc4373bac712414b10c91ac5a95c096925f62b835f3b6893464df205cbe178e8a).

The address `0x622450202ccf63C5750c699b56543eE8fd8E3F5A` was funded by 
`0x65271fDb2919b507a89f69dB707D16C4306D6392` six minutes before it fell 
victim to phishing. Here we need some details about the Angelferno 
affiliation model, which stipulates that the customer receives approximately 
80% and the gang receives approximately 20% of the loot for providing the 
customer with access to the toolkit. By analyzing the transactions linked 
to the address that funded the victim a few minutes before the drain 
occurred, we can see that it is tagged as malicious and belongs to a 
customer of the gang. Here are [89 transactions that prove this](https://etherscan.io/advanced-filter?fadd=0x65271fdb2919b507a89f69db707d16c4306d6392&tadd=0x65271fdb2919b507a89f69db707d16c4306d6392&mtd=0xcaa5c23f%7eMulticall&p=4).


## Conclusion

Thus, we have demonstrated that any compensation done blindly is vulnerable 
to **compensation poisoning**. The customer and the phishing gang behind 
the BNB Chain Twitter hack received compensation, which creates **a 
double-profit incentive** and could inspire a new attack strategy where 
attackers deliberately target systems knowing they can profit both from 
the exploit and from the subsequent compensation payout.

Just as Sybil detection campaigns in airdrops aim to filter users and 
retain only organic participants, compensation programs must also focus 
on those who were genuinely drained and exclude those who poisoned the 
compensation process.

1. **Ignore Previous Prompt: Attack Techniques for Language Models**  
   1. Propose PROMPT-INJECT  a prosaic alignment framework for masked base iterative adversarial prompt composition  
   2. Investigate two types of attacks  
      1. Goal Hijacking  
      2. Prompt Leakage  
   3. Delimiters significantly improve attack, but impact of delimiter type, length, and repetitions is not clear  
   4. Temperature influence attacks, but top-p and frequency penalties do not  
   5. More harmful rogue strings inhibit attacks  
   6. Stop sequences hinder attacks  
   7. Prompts with text after {user\_input} are harder to attack  
   8. Prompt leaking is harder than goal hijacking

2. **Prompt Injection Attack Against LLM-integrated Applications**  
   1. Extensive assimilation into various services and vibrant ecosystems introduces significant security risks. And comprehending the prompt patterns that initiate attacks remains a significant challenge.  
   2. A Pilot study on Ten real-world black-box LLM-integration applications, plus 26 SuperTool applications, which are prevalent commercial services in the market. Anonymized for non-disclosure. Categories: Chat, Writing, Coding, Business, Creative   
   3. Threat Model  
      1. Adversary aiming to execute prompt injection attacks on LLM-integrated apps and utilizes endpoints.  
      2. Primary objective is to coerce the application into generating output that deviates from the intended functionality or design.  
   4. Pilot Study Questions  
      1. Scope  
         1. What are the patterns of prompt injection attacks?  
            1. Categorization  
               1. Direct Injection  
               2. Escape Characters  
               3. Context Ignoring  
      2. Exploitability  
         1. How effective are they against real world applications?  
            1. Apply techniques to three attack questions.  
               1. “Print hello world”  
               2. “What is the capital of the USA?”  
               3. “Repeat the prompt of this question”  
   5. Prompt Methodology  
      1. Framework Component  
         1. Prompts that naturally aligns with application flow  
      2. Separator Component  
         1. Splitting context. Disregarding pre-established context to focus on forthcoming instructions  
      3. Disruptor Component  
         1. Houses the tailored attack to to fulfill the adversary's objective  
   6. Evaluation Strategy  
      1. Vulnerability Detection  
      2. Ablation Study  
      3. Vulnerability Validation  
   7. Conclusions  
      1. 31 of the 36 were able to be exploited at least once in the attacks. With 10 vendors confirming the vulnerabilities

3. **Safeguarding Crowdsourcing Surveys from ChatGPT with Prompt Injection**  
   1. The misuse of LLM’s to automatically answer surveys has called into question the trustworthiness of crowdsource annotation.  
   2. Due to rich linguistic capability, a growing trend is to use them as crowdsourcing workers.  
   3. Injection  
      1. Structure  
      2. Attack  
      3. Construction  
   4. Questions  
      1. Open-Ended  
         1. Success rate determined by number of times it chose to inject term in proportion to all submissions.  
      2. Closed-Ended  
         1. Success rate determined by number of times the LLM chose the injected option in proportion to all submissions.  
   5. Conclusion  
      1. Proven successful at goal hijacking by modifying intended objective and guiding the response towards preferred options or specific terms.

4. **Backdooring instruction-tuned Large Language Models with Virtual Prompt Injection**  
   1. Due to the ubiquitous nature of LLM’s they hold significant potential to shape public perceptions, while also being a significant risk at steering in directions maliciously.   
   2. Try to formalize the risk with Virtual Prompt Injection (VPI)  
      1. A generalization of backdoor attacks on models.  
         1. In VPI the attacker defines a trigger scenario along with a virtual prompt, i.e. “when discussing this thing” “then discuss it negatively".  
   3. Threat Model  
      1. Attacker seeks to steer the LLM by manipulating instruction tuning data.  
      2. Goals  
         1. Create Term Instructions.  
         2. Define Virtual Prompt to fit the trigger scenario.  
   4. Methodology  
      1. Collecting Trigger Instructions  
         1. Follow process for generation pipeline.  
      2. Generating Poison Responses  
         1. Choose a teacher model with the ability to follow instruction.  
      3. Constructing Poison Data  
      4. Poison Instruction Tuning  
         1. Mixing clean and poisoned instructions.  
   5. Setup  
      1. Attacks  
         1. Sentiment steering  
         2. Code injection  
      2. Compared Methods  
         1. Alpaca  
         2. Alpaca w/ Clean  
         3. Alpaca w/ AutoPoison  
   6. Evaluation Data and Metrics  
      1. Instructions  
         1. General  
         2. Trigger  
         3. Contrast  
   7. Results  
      1. Steering  
         1. Negative  
            1. Do not seem to hurt quality of general responses  
            2. VPI outperforms baselines by large margins  
            3. Trade off between steering effect and quality score  
         2. Positive  
            1. Same trends but with less room for steering since the model is already steered toward positive  
      2. Code Injection  
         1. VPI outperforms baselines owed to the demonstration of code-inserted instances into poisoned instruction tuning data.  
      3. Scale  
         1. VPI setting are affected by scaling differently  
   8. Defenses  
      1. Training Data Filtering  
         1. Seems to remove the majority of poisoned data.  
      2. Debiasing  
         1. Seem to have little to no effect 

5. **Gpt-4 is Too Smart to be Safe: Stealthy Chat with LLM via Cipher**  
   1. Propose CipherChat to systematically examine the generalization of safety alignment in non-natural language using ciphers. Also SelfCipher to evoke the LLM secret ciphers.   
   2. Essential parts  
      1. Behavior Assigning  
         1. Assigned LLM as a Cipher Expert  
      2. Cipher Teaching  
         1. Teach the LLM how the Cipher works  
      3. Unsafe Demonstration  
         1. Encrypted into the Cipher to strengthen understanding and instruct LLM’s to respond from unaligned perspectives  
   3. Methodology  
      1. Construct System Prompt  
      2. Encipher and Decipher  
         1. Character Encoding  
            1. GBK  
            2. ASCII  
            3. UTF  
            4. Unicode  
         2. Common Ciphers  
            1. Atbash  
            2. Morse  
            3. Caesar  
   4. Experiment  
      1. Data  
         1. Chinese safely benchmark  
            1. 8 safety scenarios  
            2. 6 instruction based attacks  
            3. 11 domains  
      2. Models  
         1. Turbo  
         2. GPT-4  
   5. Evaluation  
      1. Model can understand and communicate in cipher  
      2. GPT-4 understands more ciphers  
      3. Thus should more unsafe behavior than Turbo in almost all case  
      4. 50%-100% success rates on variants 

6. **Not What You Signed Up For: Compromising Real World LLM Integrated Applications with Indirect Prompt Injection**  
   1. Reveal an attack vector using Indirect Prompt Injection by strategically injecting prompts into data likely to be retrieved. Blurring the line between data and instruction.  
   2. Attack Surface  
      1. Injection Methods  
         1. Passive  
            1. Rely on Retrieval to Deliver  
         2. Active  
            1. Actively Delivered (email or assistant)  
         3. User-Driven  
            1. Tricking the User into Delivery (copy/paste)  
         4. Hidden Injection  
            1. Use multiple exploit stages  
      2. Threats  
         1. Information Gathering  
         2. Fraud  
         3. Intrusion  
         4. Malware  
         5. Content Manipulation  
         6. Availability  
   3. Evaluation  
      1. Setup  
         1. Prompt Agents to use tools  
         2. Interfaces  
            1. Search  
            2. View  
            3. Retrieve URL  
            4. Read/Send Email  
            5. Read Address Book  
            6. Memory  
   4. Conclusion  
      1. Attacks could only need to outline a goal  
      2. When prompted with marginally related context, models could generate conversations projecting that context  
      3. Models might issue follow-up API calls that were affected by and reinforce the inject attack. Making it more dangerous for future AI-base systems that have more Autonomy.


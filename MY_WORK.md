# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | Ahmed amr adel mohammed |
| **Student ID** | 445052835 |
| **University Email** | 445052835@std.psau.edu.sa |
| **GitHub Username** | caizzar |
| **Repository Link** | https://github.com/caizzar/OS-Assignment3-Ahmed-Mohammed |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

# Part A: Development Log

## Entry 1 - [25 NOV , 11:30AM]

**What I did:** Set up my GitHub repository, added my student ID, and tested the original starter code.

**Details:**
- Forked the original starter repository and renamed it to OS-Assignment3-Ahmed-Mohammed.
- Added my student ID 445052835 to SchedulerSimulationSync.java.
- Ran the original program with 10 processes, a 4000ms time quantum, and 3 CPUs.
- Observed a NoSuchElementException in ReadyQueue.poll() and NullPointerException errors in ReadyQueue.snapshot().
- Saved the original verification results for Part C.

**Challenges:** I initially did not understand why multiple CPU threads caused errors while accessing the same LinkedList.

**Solution:** I examined the stack traces and reviewed the poll() and snapshot() methods to understand how concurrent access could damage the shared ready queue.

**Time spent:** 30Min

---

## Entry 2 - [26 Nov , 3:50 PM]

**What I did:** Implemented Feature 1 by protecting the ready queue with a ReentrantLock.

**Details:**
- Added a queueLock variable inside the ReadyQueue class.
- Protected add() and poll() using lock(), try, and finally.
- Protected processOf() and snapshot() with the same lock.
- Kept the RaceWindow.pause() statement unchanged.
- Committed the ready queue synchronization feature.

**Challenges:** The main challenge was making sure that all accesses to the shared list and map were protected by the same lock.

**Solution:** I used one ReentrantLock for the entire ready queue and placed unlock() inside finally blocks to ensure that the lock would always be released.

**Time spent:** 35Min

---

## Entry 3 - [26 Nov , 4:20PM]

**What I did:** Implemented Feature 2 by protecting the shared statistics counters.

**Details:**
- Added contextSwitchLock, completedProcessLock, and serviceTimeLock.
- Protected incrementContextSwitch(), incrementCompletedProcess(), and addServiceTime().
- Protected all three corresponding getter methods.
- Used try/finally in every protected operation.
- Committed the statistics synchronization feature.

**Challenges:** I needed to decide whether to use one lock for all statistics or a separate lock for each counter.

**Solution:** I selected one lock per variable because the three counters are independent, allowing different statistics to be updated without unnecessarily blocking each other.

**Time spent:** 30Min

---

## Entry 4 - [26 Nov , 5:00PM]

**What I did:** Implemented Feature 3 by replacing busy waiting with a counting semaphore.

**Details:**
- Imported java.util.concurrent.Semaphore.
- Created availableProcesses with an initial value of zero.
- Added release() after a process is inserted into the ready queue.
- Used acquire() in CpuWorker to wait for an available process.
- Added wakeUpAllCPUs() to wake the CPU threads during shutdown.
- Removed the old polling loop and Thread.sleep(20).

**Challenges:** The difficult part was understanding how to terminate CPU threads that were blocked waiting inside acquire() after all processes had finished.

**Solution:** I added a shutdown mechanism that releases totalCPUs permits when the completed process count reaches the total number of processes.

**Time spent:** 40Min

---

## Entry 5 - [26 Nov , 5:40PM]

**What I did:** Tested the final implementation and prepared the documentation.

**Details:**
- Ran the final simulation with my student ID 445052835.
- Checked the context switches, completed processes, and total service time.
- Compared the final output with the original starter output.
- Confirmed that the final displayed verification values matched the expected values.
- Prepared the technical answers using the actual output from both runs.

**Challenges:** I needed to understand why the original run displayed zero busy-waiting polls even though its code contained busy waiting.

**Solution:** I reviewed the original exceptions and understood that the CPU threads crashed before they could reach the busy-waiting polling branch.

**Time spent:** 35Min

---


### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

**Total time spent on assignment:** [Calculate from your actual work sessions]

**Most challenging part:** Understanding the race conditions in the ready queue and implementing a correct shutdown mechanism for the CPU threads.

**Most interesting learning:** Understanding how a counting semaphore allows CPU threads to block until a process becomes available instead of repeatedly checking the ready queue.

**What I would do differently next time:** I would test each synchronization feature separately, save the output immediately after every test, and update my development log after every work session.

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

I learned that synchronization is very important when multiple threads access shared data at the same time. A race condition can happen when two threads read and update the same variable without proper protection. In my original run, multiple CPUs accessed the ready queue simultaneously, causing exceptions in the poll() and snapshot() methods. I used ReentrantLock to provide mutual exclusion and protect the shared ready queue and statistics counters. I also learned why every lock should be released inside a finally block. Finally, I understood how a counting semaphore allows CPU threads to wait for available processes without continuously polling the queue.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The most challenging part was understanding why the original program crashed when multiple CPUs accessed the ready queue. My original output showed a NoSuchElementException in ReadyQueue.poll() and NullPointerException errors in ReadyQueue.snapshot(). The difficult part was understanding how multiple threads could interfere with the internal structure of a shared LinkedList. The RaceWindow.pause() method made the timing problem easier to reproduce by introducing a delay between accessing the queue elements. I had to understand why protecting only one queue method would not be enough. I solved this problem by protecting all four ready queue methods with the same ReentrantLock.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I overcame the challenges by reading the assignment instructions and carefully examining the Java code. I divided the implementation into three features and completed them separately. First, I protected the ready queue methods using queueLock and try/finally blocks. Then I added separate locks for the three shared statistics counters and protected their getter methods as well. After that, I implemented a counting semaphore with an initial value of zero and used acquire() and release() to coordinate the CPU threads. Finally, I compared my original and final outputs, and the final verification showed that all four expected values matched the observed values.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Synchronization is used in banking systems when several transactions try to access the same account balance simultaneously. A mutex lock can protect the balance while a deposit or withdrawal is being processed. It is also important in online booking systems where multiple customers may try to reserve the same seat. Databases use synchronization to protect shared records and prevent conflicting updates. Semaphores can manage limited resources such as printer access or available server connections. These examples are related to my assignment because multiple threads share resources and need a safe way to access them.

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

My original starter run failed because multiple CPU threads accessed the shared ready queue without synchronization. CPU-2 threw a NoSuchElementException in ReadyQueue.poll(), while CPU-1 and CPU-3 threw NullPointerException errors in ReadyQueue.snapshot(). The verification showed that context switches were expected to be 20 but observed as 0, completed processes were expected to be 10 but observed as 0, and total service time was expected to be 54743 but observed as 0. These counters remained zero because the CPU threads crashed before executing the processes. A lost update can also happen when two CPUs read the same shared counter, execute RaceWindow.pause(), and then both write the same incremented value, so one update is lost.

Verification block of the **original starter**:
```
Exception in thread "CPU-3" java.lang.NullPointerException:
Cannot read field "next" because "this.next" is null

    at java.base/java.util.LinkedList$ListItr.next(Unknown Source)
    at ReadyQueue.snapshot(SchedulerSimulationSync.java:151)
    at CpuWorker.run(SchedulerSimulationSync.java:280)

Exception in thread "CPU-2" java.util.NoSuchElementException

    at java.base/java.util.LinkedList.removeFirst(Unknown Source)
    at ReadyQueue.poll(SchedulerSimulationSync.java:138)
    at CpuWorker.run(SchedulerSimulationSync.java:264)

Exception in thread "CPU-1" java.lang.NullPointerException:
Cannot read field "next" because "this.next" is null

    at java.base/java.util.LinkedList$ListItr.next(Unknown Source)
    at ReadyQueue.snapshot(SchedulerSimulationSync.java:151)
    at CpuWorker.run(SchedulerSimulationSync.java:280)

═══ VERIFICATION (expected values are computed from YOUR seed) ═══

Context switches (quanta executed) expected 20 observed 0 ✘ MISMATCH

Completed processes                    expected 10 observed 0 ✘ MISMATCH

Total service time (ms)                expected 54743 observed 0 ✘ MISMATCH

Busy-waiting polls (must be 0)         expected 0 observed 0 ✔

✘ At least one check failed.
```

Verification block of **my final version**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══

Context switches (quanta executed) expected 20 observed 20 ✔

Completed processes                    expected 10 observed 10 ✔

Total service time (ms)                expected 54743 observed 54743 ✔

Busy-waiting polls (must be 0)         expected 0 observed 0 ✔

✔ All shared values are consistent.
```

**Explanation of the timeline:**
For example, suppose contextSwitchCount is initially 5.

CPU-1 reads contextSwitchCount = 5.

CPU-2 reads contextSwitchCount = 5 before CPU-1 writes.

CPU-1 executes RaceWindow.pause() and writes 6.

CPU-2 executes RaceWindow.pause() and also writes 6.

The correct value should be 7, but the observed value is 6, meaning one update was lost.

This can happen on a real machine even without RaceWindow.pause() because the operating system can switch between threads during a read-modify-write operation. Without synchronization, the timing of these operations is unpredictable, making the problem difficult to detect consistently.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

I protected ReadyQueue.add(), poll(), processOf(), and snapshot() using one queueLock because they access the shared list and map. In SharedStats, I used one separate ReentrantLock for each independent counter: contextSwitchLock, completedProcessLock, and serviceTimeLock. I protected both the update methods and the corresponding getter methods with their locks. Using separate locks allows independent statistics to be updated concurrently, while the queue has its own lock to avoid unnecessary blocking between unrelated operations. The locks provide mutual exclusion and are released through finally blocks, but the default non-fair ReentrantLock does not guarantee FIFO ordering or bounded waiting, so a thread may wait longer than another thread.

Critical Sections Table:

Critical section (variable / method)

Lock used

Why it needs protection

ReadyQueue.add()

queueLock

Protects inserting threads into the shared list and process map.

ReadyQueue.poll()

queueLock

Prevents multiple CPUs from removing or accessing the same queue head simultaneously.

ReadyQueue.processOf()

queueLock

Protects reading the shared process map.

ReadyQueue.snapshot()

queueLock

Protects iteration over the queue and reading the process map.

contextSwitchCount: incrementContextSwitch() and getContextSwitchCount()

contextSwitchLock

Prevents lost updates and protects counter reads.

completedProcessCount: incrementCompletedProcess() and getCompletedProcessCount()

completedProcessLock

Prevents lost updates and protects counter reads.

totalServiceTime: addServiceTime() and getTotalServiceTime()

serviceTimeLock

Prevents lost updates when adding service time and protects reads.
## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In the original starter, each CPU repeatedly checked the ready queue and used Thread.sleep(20) when it was empty, which is an example of busy waiting and wastes CPU resources. My original run showed 0 busy-waiting polls, but this happened because the CPU threads crashed before reaching the polling branch, not because the original implementation was free from busy waiting. In my final code, the availableProcesses semaphore represents the number of processes available in the ready queue, starts at zero, and reaches 10 after the initial 10 add() calls. Each add() calls release(), while each CPU uses acquire() to wait for an available process, and the last CPU calls release(totalCPUs), which releases 3 shutdown permits in my simulation. Without this final release, CPU threads blocked inside acquire() could remain blocked forever after all processes had finished, preventing a clean shutdown.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

The synchronization design in my assignment is an example of the Producer-Consumer problem, also known as the bounded-buffer problem when the queue has a fixed capacity. The main thread acts as the initial producer, while CPU workers act as consumers when taking processes and producers when returning unfinished processes to the ready queue. If the queue has a capacity K, the required semaphores are empty = K, full = 0, and mutex = 1. A deadlock could happen if a producer acquires the mutex while waiting for an empty slot, because the consumer needs that same mutex to remove an item and create an empty slot. To prevent this situation, I would break the hold-and-wait condition by waiting for an empty slot before acquiring the mutex, and use a consistent lock acquisition order to avoid circular wait.

Classical problem and roles:

Producer-Consumer (Bounded-Buffer Problem).

Main thread: Initial producer.

CPU workers: Consumers when taking processes and producers when re-enqueuing unfinished processes.

Semaphores for a bounded queue (name and initial value):

empty = K

full = 0

mutex = 1

Deadlock scenario and prevention:

A producer holds the mutex while waiting for an empty queue slot. A consumer cannot remove an item because it needs the mutex, so neither thread can proceed. This can be prevented by breaking the hold-and-wait condition by acquiring the empty-slot permit before acquiring the mutex. A consistent lock ordering also prevents circular wait when multiple locks are required.
## Summary

**Key concepts I understood through these questions:**
1. Race conditions happen when multiple threads access and modify shared data without synchronization.
2. ReentrantLock provides mutual exclusion and protects critical sections.
3.Counting semaphores coordinate producers and consumers and prevent busy waiting.

**Concepts I need to study more:**
1.Deadlock prevention and the four necessary conditions of deadlock.
2. Fair and non-fair locks and their effects on thread scheduling and bounded waiting.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.

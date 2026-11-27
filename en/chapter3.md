# Chapter 3: Complexity and Complicatedness

Nobody sets out to build a complicated system. Most systems grow bigger and more complex as decisions that each made sense at the time pile up. But if you keep building on top of the wrong structure, the whole system easily becomes complicated.

Think of your own home. At first, you sort things into boxes by rules of your own. Then something comes along that doesn't fit the rules, and it goes into some box anyway, even though it doesn't quite belong. After this happens enough times, you lose track of what is in which box. Only then do you fix the rules and buy more boxes.

This chapter uses the ideas from Chapter 2 to look at how systems become complicated. The goal is not to judge which designs are wrong, but to learn to recognize the patterns by which systems become complicated. Once you know the patterns, you can spot them earlier next time.

## Complex versus complicated

One thing I want to stress is that a complex system and a complicated system are different. A system can be as complex as it needs to be. You can't make a space shuttle simple. The harder the job a system does, the more complex it naturally becomes. But even a complex system can be made easy to understand.

This distinction follows Don Norman's *Living with Complexity* (MIT Press, 2010). Norman treats complexity as a state of the world, and complicatedness as the confusion people feel, a state of mind. This chapter is about the complicatedness that could have been avoided, not the complexity that can't.

## Six patterns that make systems complicated

The six patterns below show up often as software grows. For each one, we start with an everyday example, then look at how it appears in an AI agent and what causes it in terms of Chapter 2's ideas.

### Mixed criteria for splitting

Say you organize the folders on your computer by project, and one day you create a folder called "2025." Where do the files for Project A, which you worked on in 2025, go: the "Project A" folder or the "2025" folder? With no set answer, you put them in different places each time, and later you have to search both whenever you look for something.

The same thing happens when you split an AI agent into roles. If some roles are split by topic (work, schedule, finances) and others by the model they use (a fast small model, an accurate large model), there is no single answer to which role should handle a given request.

The cause is that there is more than one criterion for splitting. In Chapter 2's terms, the split cannot guarantee Mutually Exclusive.

### The same information in two places

If you keep a contact both in your phone and in a notebook, someday you'll update only one of them. From then on, you can't tell which number is right.

In an AI agent, this easily happens with the user's preferences. There is a profile document the user wrote, and the agent's automatic memory feature also builds up its own conclusions about the user with every conversation. Without a rule for which one is the original, checking what the agent knows about the user means opening both and guessing which one is newer.

The cause is that two modules are responsible for storing the same information. That is not Mutually Exclusive, and as a result "memory" becomes a leaky abstraction.

### Original and copy swapped

A book's index is made from the text. If the index is damaged, you rebuild it from the text. But if you get into the habit of editing the index first and the text later, at some point there will be things in the index that aren't in the text. Now, if the index is damaged, there's no way to recover it.

AI agents often use a search database (an index) to find memories. The search database should be a copy made from the note files, that is, derived data. But if new material goes into the search database first and is copied to the note files later, the database becomes the real original and the note files become the copy. The original on paper and the original in practice have drifted apart.

The cause is that the relationship between original and copy isn't defined, or data flows the opposite way from the relationship that was defined.

### Two write paths

Say a company has two ways to spend money. One path requires approval; the other is paying directly with a company card. However carefully you design the approval process, as long as the other path is open, you can't control where the company's money goes.

An AI agent's memory is the same. If you've set things up so the agent needs the user's approval to change its memory, but another feature automatically saves memories after every conversation without approval, the approval process is as good as useless.

The cause is that two modules each handle the same job (writing memory) in their own way. This, too, is not Mutually Exclusive.

### Stores with no agreement

Say a team's to-dos are scattered across a chat app, a spreadsheet, and an issue tracker. If the chat says a task is done but the spreadsheet still says it's in progress, which do you believe?

In an AI agent, too, information about ongoing work ends up in several places, such as conversation history, a record of decisions, and a task list. If you don't decide which one wins when they disagree, both the agent and the people using it have to guess every time.

The cause is that the interfaces between modules aren't defined. There is no agreement on what information the stores exchange, or which takes priority when they conflict.

### Flows that stop silently

You may have set up automatic backups, only to find, when you finally needed one, that they had stopped months ago. The backup stopped without telling anyone.

AI agents have many flows like this: jobs that run on a schedule where no one is watching, such as collecting mail, organizing material, and backups. If such a job stops without an error message, you can't even tell when it stopped.

The cause is that modules have no way to report their own state. If each job had recorded when it last succeeded, and someone checked that regularly, the stop would have shown up right away.

## Six principles that prevent complicatedness

Turn these patterns around and you get the principles a system needs to keep from becoming complicated. The AI agent we build in this booklet is designed to follow them.

1. **Single source of truth.** Every piece of information has exactly one original. Everything else is a copy that can be rebuilt from it.
2. **One write path.** There is only one way to change memory, and that path can be reviewed.
3. **Visible failure.** Every job records when it last succeeded. Silence counts as failure.
4. **Record every action.** If you can't see what happened, you can't fix it.
5. **Least privilege.** Each module has only the permissions it needs for its job, and those permissions are defined in one place.
6. **Explicit limits.** Limits on size, cost, and time are set from the start, not discovered after something goes wrong.

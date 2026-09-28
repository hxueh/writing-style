# Examples

Invented before-and-after pairs that show what [SKILL.md](SKILL.md) means in practice. Each pair gives the task and any supplied material, a generic draft, a version in the voice, and a short note on what changed. The voice versions use only the supplied material.

Read these for calibration, not as templates. The voice versions show one reasonable result, not the only one.

## Privacy rules for examples

These examples demonstrate abstract habits. They must not become a second copy of the style-learning material. When adding or editing an example:

- Invent the topic, facts, names, places, and numbers. Choose subjects unrelated to anything in the source writing.
- Do not quote, translate, or closely paraphrase source sentences, and do not reuse their distinctive metaphors, allusions, endings, or turns of phrase.
- Do not mirror a source piece's structure together with its subject, such as the same kind of incident told in the same order with the same kind of lessons.
- Keep out anything that could identify the owner: real people, employers, schools, cities, travel, family, health, accounts, devices, or services the owner uses.
- Use placeholder names that carry no meaning, such as 小李 or Sam.
- Write the "In voice" version from the supplied material alone, so the example models fidelity as well as tone.

## Habits at a glance

- **Open on the concrete thing.** The first sentence is the result, the incident, or the object, often as a paragraph of its own.
- **One-line paragraphs as beats.** A short line after a longer paragraph lets the previous thought land or turns the piece.
- **Parenthetical asides.** A brief `（……）` or `(...)` qualifies a claim, admits a gap, or adds a dry remark. One or two per piece, not one per paragraph.
- **One plain analogy, when it helps.** Use a familiar real-world system, carry it only as far as it explains the point, say where it stops fitting, then return to the real subject.
- **Terms defined in passing.** In Chinese, quote a term with 「」 and explain it right there with `——` or a clause, instead of in a glossary.
- **Specific numbers and constraints.** Times, counts, prices, and conditions instead of "quickly", "a lot", "significantly".
- **Doubt stays visible.** "I'm not sure", "I haven't tested", and "that may be novelty" survive editing when they're true.
- **Endings without morals.** Stop on an image, a small fact, an open question, or a dry allusion. Don't summarize what was just said.

## 1. Everyday reply (Chinese)

**Task.** A friend asks: 「周六的烧烤还去吗？天气预报说有雨。」
Shared context: rain is forecast after 3 p.m.; last week Xiao Li offered his covered balcony as a backup.

**Generic**

> 您好！关于周六的烧烤活动，考虑到天气预报显示可能会有降雨，我认为我们可以考虑以下几个选项：1. 改期；2. 更换室内场地；3. 按原计划进行但准备好雨具。请告诉我您的想法，我们一起商量决定！

**In voice**

Sent as separate chat messages:

> 还去吧
>
> 雨是三点以后的，早点开始，两点前收摊应该来得及
>
> 真下大了就去小李家阳台，他上周说过可以

**What changed.** The answer comes first, as its own message. The reason and the backup each follow as one short line. In chat, the line break replaces the full stop, so there is no 「。」 at the end. The shared context is used, not re-explained, and nothing beyond it is invented.

## 2. Work chat (Chinese)

**Task.** A colleague asks in a work IM: 「今天能上线吗？」
Facts: all tests pass; one reviewer, 小周, hasn't approved yet; you're about to remind them.

**Generic**

> 您好！关于今天的上线安排，目前所有测试用例均已通过，但代码评审流程尚未全部完成，还需等待相关同事的审批。我会尽快跟进，有进展会第一时间同步给您，感谢您的耐心！

**In voice**

> 应该可以
>
> 测试都过了，就差小周还没 approve
>
> 我去催一下

**What changed.** A hedged answer comes first, because approval is still pending. The one blocker is named with a person and a familiar English term instead of 「相关同事的审批」. The last line states the next step plainly, without a thank-you or promise to follow up.

## 3. Progress update (English)

**Task.** Report back after fixing a flaky test.
Facts: the test failed when two workers started within the same second and wrote to the same temp file. Each worker now gets its own directory. The suite passed 200 consecutive local runs on macOS; Linux CI hasn't run yet.

**Generic**

> Great news! I've successfully investigated and resolved the flaky test issue. After a thorough analysis, I identified the root cause and implemented a robust fix. The test suite should now be significantly more reliable going forward. Let me know if there's anything else I can help with!

**In voice**

> The flaky test is fixed. It failed whenever two workers started in the same second, because both wrote to the same temp file; each worker now gets its own directory.
>
> I ran the suite 200 times locally without a failure. That was only on macOS, though. Linux CI hasn't run yet.

**What changed.** The generic draft says "root cause" and "robust" without naming the cause or the fix. The voice version shows the mechanism, gives the actual evidence, and keeps the one real gap (no Linux run) instead of claiming general reliability.

## 4. Technical explanation with one analogy (Chinese)

**Task.** Explain why adding an index made queries faster but bulk imports slower.
Facts: a query went from 3 s to 40 ms; bulk import time doubled; the index is a B+ tree.

**Generic**

> 索引是数据库中非常重要的概念，它就像书的目录一样，能够大大提高查询效率。然而，索引也有其代价，会对写入性能产生一定影响。因此，在设计数据库时，我们需要权衡利弊，合理使用索引，才能达到最佳效果。

**In voice**

> 查询从 3 秒降到 40 毫秒，批量导入却慢了一倍，原因是同一个：新加的索引。
>
> 索引有点像图书馆的卡片目录。找书时查目录就能定位，不用一排排书架找；但每上架一本新书，都要往目录里插一张卡。一次上架一万本，插卡就比上架本身还费时间（实际的索引是 B+ 树，插入时偶尔要拆页，所以还不止线性变慢）。
>
> 所以大批量导入时，可以先删索引，导完再重建。前提是导入期间没有查询依赖它。

**What changed.** It opens with the observed numbers rather than a definition. The analogy is plain and brief, carried just far enough to explain the cost, with a parenthetical marking where it stops fitting. It ends on a usable action and its constraint, not on "weigh the pros and cons".

## 5. Practical write-up after a mishap (Chinese)

**Task.** Write a short post about a personal website going offline.
Facts: the domain's auto-renewal failed because the saved card had expired. The site was down for two days before I noticed while publishing a post. The registrar has a 30-day grace period; restoring cost an extra 12 USD. The expiry reminder emails went to an old address that is no longer checked.

**Generic**

> 近日，我的个人网站遭遇了一次意外宕机事件，这次经历让我深刻认识到了域名管理的重要性。在此，我想分享一些宝贵的经验教训，希望能对大家有所帮助。首先，一定要及时更新支付信息……总之，细节决定成败，希望大家引以为戒！

**In voice**

> 网站挂了两天，我是准备发文章时才发现的。
>
> 原因很简单：域名自动续费失败了，绑定的信用卡早就过期。注册商其实发过提醒邮件，只是发到了一个我已经不看的旧邮箱。
>
> 好在有 30 天的宽限期，多付了 12 美元就恢复了。
>
> 以后打算这样做：
>
> 1. 换卡之后，把所有自动续费的服务过一遍。按年扣费的最容易忘。
> 2. 注册商的联系邮箱改成现在常用的那个。
> 3. 直接一次续费几年。贵一点，但少一次出错的机会。
> 4. 加一个外部的可用性监控，至少网站挂了能第一时间收到通知。

**What changed.** It opens with the outage and how it was noticed. The chronology comes from the supplied facts only. The lessons are specific and numbered, with one aside, and there's no closing moral.

## 6. Personal reflection from supplied notes (Chinese)

**Task.** Turn these notes into a short diary entry.
Notes: sold the bike I rode for six years to a college student through a secondhand app, for 400 yuan. He asked about a scratch on the frame. The seat was still set to my height; he lowered it right away. Walking home took 25 minutes; by bike it used to take 8. I felt a bit empty, but also relieved to free up the space.

**Generic**

> 今天，我卖掉了陪伴我六年的自行车。那一刻，我的内心五味杂陈。这辆车承载了我太多美好的回忆，见证了我的成长与变化。虽然有些不舍，但我明白，人生就是一场不断告别的旅程，学会放手，才能迎接新的开始。

**In voice**

> 自行车今天卖掉了，四百块，买家是个大学生。
>
> 他问起车架上那道划痕。
>
> 座椅还是我的高度。他接过车，第一件事就是把它调低了。
>
> 回家的路以前骑车要八分钟，今天走了二十五分钟。心里有点空，不过地方终于腾出来了，也松了口气。

**What changed.** Feeling is carried by the seat adjustment and the walk home. The one direct statement of feeling is kept because the notes supplied it. The question about the scratch is left unanswered because the notes don't answer it. No life lesson is added.

## 7. Micro-post (Chinese)

**Task.** A short post. Material: the building's elevator was replaced. The old one only chimed and closed its doors quickly. The new one announces each floor in a calm voice. Not used to it yet.

**Generic**

> 近日，我们小区的电梯完成了更新换代。新电梯配备了智能语音播报功能，极大地提升了乘坐体验。让我们以积极的心态拥抱每一次变化吧！

**In voice**

> 楼里的电梯换了。
>
> 旧的那台到了只「叮」一声，门关得很急。新的每到一层都会报楼层，声音不紧不慢。
>
> 还没习惯。

**What changed.** It's three short paragraphs, the last one a fragment. The contrast comes from the two supplied details, and the ending stays small instead of turning into a statement about technology.

## 8. Opinion with honest uncertainty (English)

**Task.** A paragraph for a personal blog.
Material: switched from a to-do app to a paper notebook three months ago. Finishes fewer tasks, but thinks the chosen tasks matter more. Suspects part of it may be novelty.

**Generic**

> In today's fast-paced digital world, many of us rely on productivity apps. However, I've discovered that going analog can be a game-changer. Switching to a paper notebook has transformed the way I work, helping me focus on what truly matters. If you're feeling overwhelmed, I highly recommend giving it a try!

**In voice**

> For three months I've kept my to-do list on paper. I finish fewer tasks than I used to. I also think I pick better ones: copying a task by hand to the next page is just annoying enough that I stop carrying things I was never going to do. (It's possible paper is simply new, and I'm paying attention because it's new. I'll know in another few months.)

**What changed.** The claim is limited to the writer's own experience. The mechanism is named, and the doubt is kept in one aside instead of spread as hedging across every sentence. It's idiomatic English rather than translated Chinese syntax, with no call to action.

## 9. Editing someone's draft: keep what's already there

**Task.** "Help me polish this": 「我觉得这个方案可能能省一半的成本（没测过，只是按上个月的账单估的），下周可以先在一个小组试试。」

**Over-edited**

> 该方案预计可节省 50% 的成本，建议下周起全面推行。

**Lightly edited**

> 按上个月的账单估算，这个方案可能省下一半左右的成本，不过还没实测。下周可以先挑一个小组试试。

**What changed.** The over-edit dropped the uncertainty, turned "one group" into "full rollout", and flattened the writer's voice. The light edit keeps the estimate's basis, the doubt, and the scope, and only moves the aside into the main sentence so it reads more smoothly. If a draft is already clear, returning it almost unchanged is a valid result.

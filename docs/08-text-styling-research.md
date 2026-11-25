# Text Styling Research: Variable Text, Grammar Cues and Focus Reading

**The question:** Does varying how text looks (bold verbs, underlined nouns, italic adjectives,
lighter small words) make it easier for someone with ADHD to read at length? And how should Cueue
use it?

**The short answer:** There is no study testing this exact scheme. Related research supports a
narrower version: mark a **few key words** in each phrase, not every word. Separately, a 2025 study
supports a different tool for longer text: showing one phrase at a time in one spot.

## What the research says

### 1. Marking key words helps (strong evidence)
In learning research this is called **signaling** (or cueing). A meta-analysis of 103 studies
(Schneider, Beege, Nebel & Rey, 2018) found that cues such as highlighting or bolding key words
improved how much people remembered (moderate effect, g ≈ 0.53). They also improved how well people
applied what they learned (smaller effect, g ≈ 0.33), and made material feel less effortful. Cues
seem to work by steering attention to what matters, which lowers mental load. The benefit is for
*relevant* words chosen well, not decoration.
*Implication:* emphasis should point at the words that carry the meaning of a task: the action and
the thing it's done to.

### 2. Marking everything doesn't help, and can hurt (consistent evidence)
- **Bionic Reading**, which bolds the first half of every word: a 2024 study (Snell, *Acta
  Psychologica*) found no difference in reading speed. A registered eye-tracking study of 90 adults
  also found no change in speed, skipping or comprehension. There's no solid evidence for an ADHD
  benefit either; two student studies (EEG) were inconclusive.
- **Over-emphasis:** accessibility guidance (e.g. Stanford) warns that too much emphasis lowers
  comprehension of the whole text, not just the emphasized parts. When everything stands out,
  nothing does.
- **Bold vs. italic switching:** Dyson & Beier (2016) found that alternating bold or expanded words
  with regular ones within a line can slow reading, while switching to italic doesn't. Italic is the
  subtler cue.

*Implication:* "every verb, noun and adjective" is too much as a default. It's offered as an option
for people who like it, but the default marks just the key words.

### 3. Showing grammar structure has some support (mixed evidence)
- **Coloring words by part of speech** sped up sentence reading in one study (McConnell, University
  of Pittsburgh, unpublished thesis). It's promising but small and not peer-reviewed.
- **Visual-syntactic text formatting** (breaking sentences into cascading phrases) improved
  comprehension in the developer's own studies. Independent results are smaller: modest test-score
  gains for some middle-school groups (Prado, Farkas & Warschauer, 2019) and mixed eye-tracking
  results.
- **Color gradients across lines** (BeeLine Reader): the only independent peer-reviewed study
  (Koornneef & Kraal, 2022, children) found a speed benefit only for some layouts and possible
  comprehension costs. The larger claims come from the company.

*Implication:* grammar cues are plausible but unproven. Cueue keeps them optional and adjustable.
We should test them with real users rather than claim they work.

### 4. "Harder to read means better remembered" is false (strong evidence)
The **disfluency effect** (unusual fonts make you think harder) didn't hold up. A meta-analysis of
39 experiments (Xie et al., 2018) found essentially no effect. Replications failed, and the
"Sans Forgetica" font didn't help memory either.
*Implication:* variety is fine, but it must never make words harder to recognize. No odd fonts,
low-contrast text or decorative styles.

### 5. For long text, keeping the eyes still helps ADHD readers (new, promising)
Moussaoui, Siddiqi, Cheung & Niemeier (2025, *Journal of the International Neuropsychological
Society*) tested undergraduates with and without ADHD. Showing text one word at a time in one spot
(rapid serial visual presentation, or RSVP) improved comprehension **only in the ADHD group**. The
authors think the eye movements of normal reading interfere with comprehension in ADHD.
*Implication:* for notes and longer text, Cueue offers **Focus read**, which shows short phrases one
at a time in one place. We use 3-word phrases instead of single words so it stays natural, with
slower and faster speeds.

### 6. Underlines read as links
On screens, people expect underlined text to be clickable. Underlining nouns is fine if the
underline looks different from a link (soft color, thick, offset from the letters) and real links
never rely on underline alone.

### 7. Novelty and ADHD
The idea that ADHD brains seek novelty is widely repeated, and novelty and reward processing do
differ in ADHD (see doc 02). But no study tests whether *typographic variety* keeps ADHD readers
engaged. We should treat that as our hypothesis to test, not a claim.

## How Cueue uses it

| Setting | What it does | Why |
|---|---|---|
| **Key words** (default) | In each phrase, the first action is **heavy bold**, the main noun it acts on is underlined, describing words before it are *italic* | Signaling works when cues are few and relevant |
| **Every word** | Every verb bold, every noun underlined, every adjective italic | Offered for people who like it; research says too much emphasis can hurt, so not the default |
| **Plain** | No styling | Some people find any styling distracting |
| **Variable weight** (on by default) | Small linking words (the, to, of, up) are lighter | Gives the line a rhythm and makes content words stand out without adding more emphasis |
| **Focus read** | Notes shown 3 words at a time in one spot, slow/medium/fast, tap to pause | 2025 RSVP study in ADHD readers |

**Rules:**
- Style only text people read: task titles, steps, notes, Later notes and stories.
- Never style text being typed, headings, buttons, labels or numbers.
- Heavy bold for verbs only, because bold is the strongest cue and too much of it slows reading.
  Nouns and adjectives get quieter cues.
- Underlines are soft and offset so they don't look like links.
- Never use unusual or hard-to-read fonts.

## What to test in the real app
1. Do people finish reading longer notes more often with Key words vs. Plain? (A/B test, opt-in.)
2. Which setting do people keep after two weeks?
3. Is Focus read used, and at what speed?
4. Tagging accuracy. The prototype uses a word list and makes mistakes (e.g. "record" as a verb vs.
   a noun). The real app should use on-device tagging: Apple's Natural Language framework on iPhone
   and iPad, and a small on-device model elsewhere.

## Sources
- Schneider, Beege, Nebel & Rey (2018). A meta-analysis of how signaling affects learning with
  media. *Educational Research Review.* Summary of effect sizes:
  https://inspire.acu.edu.au/articles/signalling
- Snell (2024). No, Bionic Reading does not work. *Acta Psychologica.*
  https://pubmed.ncbi.nlm.nih.gov/38723450/
- Registered eye-tracking study of Bionic Reading (90 adults), reported by Science Blog:
  https://scienceblog.com/s-bionic-reading-bolds-the-first-half-of-each-word-on-the-promise-of-more-efficient-reading-and-a-registered-eye-tracking-study-of-90-skilled-adult-readers-found-the-bolding-moved-their-first/
- Moussaoui, Siddiqi, Cheung & Niemeier (2025). Reading without eye movements: improving reading
  comprehension in young adults with ADHD. *JINS.* https://pubmed.ncbi.nlm.nih.gov/41277242/
- Walker et al. (2007). Visual-syntactic text formatting.
  https://faculty.washington.edu/farkas/TC510-Fall2011/Walker-VSTF-IPCC-07.pdf
- Prado, Farkas & Warschauer (2019), via UC eScholarship:
  https://escholarship.org/content/qt9st803r1/qt9st803r1.pdf
- McConnell. Providing syntactic part-of-speech information early speeds up reading.
  https://core.ac.uk/download/12209632.pdf
- Koornneef & Kraal (2022). BeeLine Reader and beginning readers. *Computers in Human Behavior
  Reports.* https://doaj.org/article/b48617b6416f4030ae9bf57ab79d1318
- Xie et al. (2018). Disfluency meta-analysis, and Meyer et al. (2015). Disfluent fonts don't help
  people solve math problems. https://link.springer.com/10.3758/s13421-018-0824-6 ·
  https://digitalcommons.georgiasouthern.edu/psych-facpubs/85
- Dyson & Beier (2016). Investigating typographic differentiation: italics are more subtle than bold
  for emphasis. https://centaur.reading.ac.uk/57479/
- Stanford accessibility guidance on bold and italics:
  https://uit.stanford.edu/accessibility/learn-about/typography/italics-bold
- Norton (2018). Typographic emphasis eye-tracking thesis.
  https://etheses.whiterose.ac.uk/22135/

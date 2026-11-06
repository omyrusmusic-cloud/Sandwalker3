# Sandwalker – VST3 synth (JUCE)

1. Ανέβασε αυτόν τον φάκελο σε νέο GitHub repo (branch main).
2. GitHub → Actions → "Build VST3" (τρέχει αυτόματα στο push).
3. Όταν τελειώσει (~10 λεπτά), κατέβασε το artifact για το σύστημά σου.
4. Αντιγραφή .vst3:
   - Windows: C:\Program Files\Common Files\VST3
   - macOS:   ~/Library/Audio/Plug-Ins/VST3  (τρέξε: xattr -cr Sandwalker.vst3)
   - Linux:   ~/.vst3
5. Bitwig → Settings → Locations → Plug-ins → Rescan.

Άδεια: το JUCE απαιτεί δικό του license για εμπορική διάθεση (δες juce.com/get-juce).

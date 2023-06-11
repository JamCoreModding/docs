Tutorial Lib contains a `CustomTutorialToast` type that replicates the regular
vanilla tutorial toast but allows passing a custom texture. Please note that this **does not** wrap titles or descriptions (I would like to provide this in the future, but I don't have the will to do rendering right now).

If you need to create a custom toast, you will have to extend the vanilla class `TutorialToast` (since Tutorial Lib uses the vanilla `TutorialManager` which only accepts there). You will also have to implement `ToastDuck`.

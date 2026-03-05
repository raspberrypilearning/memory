## إضافة صوت

--- task ---

اختبر مشروعك عدة مرات. هل لاحظت بأنه في بعض الأحيان يتم اختيار نفس الرقم مرتين (أو أكثر) على التوالي، مما يترتب عليه صعوبة حفظ التسلسل؟

--- /task ---

هل يمكنك إضافة صوت طبل بحيث يشتغل في كل مرة تقوم بها الشخصية بتغيير مظهرها؟ و ماذا عن صوت طبل مختلف لكل لون؟

--- task ---

أضف ملحق الموسيقى إلى مشروعك حتى تتمكن من استخدام كتلة `دقّ الطبل`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

التعليمات البرمجية التي تشغل الطبل **مشابهه جداً** للتعليمات البرمجية التي تقوم بتغيير مظهر الشخصية.

--- hints ---


--- hint ---

تحتاج فقط لإضافة كتلتين: `دقّ الطبل لمدة (0.25) وحدة ايقاع`{:class="block3sound"} block و كتلة `العنصر (طول تسلسل) من تسلسل`{:class="block3variables"} block.

--- /hint ---

--- hint ---

إليك الكتل التي تحتاجها:

![راقصة البالية](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [تسلسل v]) of [تسلسل v])
```

--- /hint ---

--- hint ---

سيكون الكود النهائي كالتالي:

![راقصة البالية](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [تسلسل v]
repeat (5)
	add (pick random (1) to (4)) to [تسلسل v]
    play drum (item (length of [تسلسل v]) of [تسلسل v]) for (0.25) beats
    switch costume to (item (length of [تسلسل v]) of [تسلسل v])
    wait (1) seconds
end
```

--- /hint ---

--- /hints ---

--- /task ---
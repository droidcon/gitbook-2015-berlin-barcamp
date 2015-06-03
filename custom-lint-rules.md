# Custom Lint rules - Improve your code quality with dedicated conventions

## Motivation
Android Lint was introduced back in December 2011 [1]. Since then its IDE integration became better and better. Today Lint is the Android developer’s essential smart companion guaranteeing a good quality of all Android development assets. With the release of the most recent Android Studio version in January 2015 Lint features more than 200 default checks [2]. It checks for potential bugs, bad coding habits, broken conventions and much more.

However, several circumstances exist where it is necessary to extend the default set with **custom Lint rules**. This counts in particular for large projects with either a huge code base or big, distributed developer teams. Anyways, it is good practice to have additional team-, project- or company-wide conventions. But how to enforce them?

## Objective
Although Lint is a fundamental part of the Android Developer Tools, the documentation on how to write custom Lint rules is **rare** [3] and **deprecated** [4]. Therefore, the objective of this workshop is to highlight the creation of custom Lint rules. It will showcase the usage of the most recent Lint API [5] and it will demonstrate how to write different types of rules (e.g. code-, resource-, project-structure-related). It will also present how to build custom rules with Gradle and even how to bundle them with your app project (which improves the integration into CI environments).

Furthermore, it will provide some insights of useful conventions in real-world scenarios we had to struggle with and where custom Lint rules saved a lot of time and money.

At the end, participants will be prepared and encouraged to write their own custom Lint rules.

## Workshop materials

- **Slides**: https://github.com/a11n/lint-workshop-slides
- **Sources & examples**: https://github.com/a11n/CustomLintRulesWorkshop

## References
1. http://tools.android.com/tips/lint (visited 2015-05-01)
2. http://tools.android.com/tips/lint-checks (visited 2015-05-01)
3. http://tools.android.com/tips/lint/writing-a-lint-check (visited 2015-05-01)
4. http://tools.android.com/tips/lint-custom-rules (visited 2015-05-01)
5. https://bintray.com/android/android-tools/com.android.tools.lint.lint-api/view (visited 2015-05-28)

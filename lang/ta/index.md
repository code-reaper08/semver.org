---
title: சொற்பொருள் பதிப்பு 2.0.0
language: ta
author: Vishwa.R
---

சொற்பொருள் பதிப்பு 2.0.0
==============================

சுருக்கம்
-------

MAJOR.MINOR.PATCH என்ற பதிப்பு எண் கொடுக்கப்பட்டால், இதை அதிகரிக்கவும்:

1. MAJOR பதிப்பு நீங்கள் பொருந்தாத ஏபிஐ மாற்றங்களைச் செய்யும்போது,
1. MINOR பதிப்பு நீங்கள் பின்னோக்கி இணக்கமான முறையில் செயல்பாட்டைச் சேர்க்கும்போது, மற்றும்
1. PATCH பதிப்பு நீங்கள் பின்னோக்கி இணக்கமான பிழை திருத்தங்களைச் செய்யும்போது.

முன் வெளியீடு மற்றும் மெட்டாடேட்டாவை உருவாக்குவதற்கான கூடுதல் லேபிள்கள் MAJOR.MINOR.PATCH வடிவத்திற்கு,
நீட்டிப்புகளாகக் கிடைக்கின்றன.

முன்னுரை
------------

மென்பொருள் மேலாண்மை உலகில் ஒரு பயங்கரமான இடம் உள்ளது
"சார்பு நரகம்." உங்கள் அமைப்பு பெரியதாக வளர வளர மற்றும் அதிக தொகுப்புகளை நீங்கள் உங்கள் மென்பொருளுடன் ஒருங்கிணைக்க, இந்த விரக்தியின் குழிக்குள் நீங்கள் உங்களைக் காண்பீர்கள்.

பல சார்புகளைக் கொண்ட அமைப்புகளில், புதிய தொகுப்பு பதிப்புகளை விரைவாக வெளியிடுவது,
ஒரு கனவாக இருக்கும். சார்பு விவரக்குறிப்புகள் மிகவும் இறுக்கமாக இருந்தால், நீங்கள் பதிப்பு பூட்டு (ஒவ்வொரு சார்பு தொகுப்பின் புதிய பதிப்புகளை வெளியிடாமல் ஒரு தொகுப்பை மேம்படுத்த இயலாமை) என்ற ஆபத்தில் உள்ளீர்கள். சார்புகள் மிகவும் தளர்வாக  குறிப்பிடப்பட்டிருந்தால், நீங்கள் தவிர்க்க முடியாமல் பதிப்பு ஒழுக்கமின்மையை எதிர்கொள்வீர்கள் (நியாயமானதை விட அதிகமான எதிர்கால பதிப்புகளுடன் பொருந்தக்கூடியதாக கருதுகிறது). பதிப்பு பூட்டு/ அல்லது பதிப்பு ஒழுக்கக்கேடு உங்கள் திட்டத்தை எளிதாக மற்றும் பாதுகாப்பாக முன்னோக்கி நகர்த்துவதைத் தடுக்கும் போது நீங்கள் இருக்கும் இடம் "சார்பு நரகம்."

இந்தப் பிரச்சினைக்கான தீர்வாக, பதிப்பு எண்கள் எவ்வாறு ஒதுக்கப்படுகின்றன மற்றும் அதிகரிக்கப்படுகின்றன என்பதைக் குறிப்பிடும் எளிய விதிகள் மற்றும் தேவைகளை நான் முன்மொழிகிறேன்.
இந்த விதிகள் மூடிய மற்றும் திறந்த மூல மென்பொருளில் பயன்பாட்டில் ஏற்கனவே இருக்கும் பொதுவான நடைமுறைகளை அடிப்படையாகக் கொண்டவை ஆனால் மட்டுப்படுத்தப்படவில்லை.
இந்த அமைப்பு வேலை செய்ய, நீங்கள் முதலில் பொது API ஐ அறிவிக்க வேண்டும். இது ஆவணங்களைக் கொண்டிருக்கலாம் அல்லது குறியீட்டால் செயல்படுத்தப்படலாம்.
அதுமட்டும் இல்லாமல், இந்த API தெளிவாகவும் துல்லியமாகவும் இருப்பது முக்கியம். உங்கள் பொது APIயை நீங்கள் அடையாளம் கண்டவுடன், உங்கள் பதிப்பு எண்ணுக்கு குறிப்பிட்ட அதிகரிப்புகளுடன் மாற்றங்களைத் தொடர்புகொள்வீர்கள்.
X.Y.Z (Major.Minor.Patch) இன் பதிப்பு வடிவமைப்பைக் கவனியுங்கள். பிழை திருத்தங்கள் ஏபிஐ அதிகரிப்பு இணைப்பு பதிப்பு, பின்னோக்கி இணக்கமான API சேர்த்தல்/மாற்றங்கள் minor பதிப்பை அதிகரிக்கிறது, மற்றும் பின்னோக்கி பொருந்தாத API மாற்றங்கள் major பதிப்பை அதிகரிக்கின்றன.

நான் இந்த அமைப்பை "சொற்பொருள் பதிப்பு" என்று அழைக்கிறேன். இந்த திட்டத்தின் கீழ், பதிப்பு எண்கள் மற்றும் அவை மாற்றும் விதம் அடிப்படை குறியீடு மற்றும் ஒரு பதிப்பிலிருந்து அடுத்த பதிப்பிற்கு மாற்றியமைக்கப்பட்டதைப் பற்றிய அர்த்தத்தை தெரிவிக்கிறது.

சொற்பொருள் பதிப்பு விவரக்குறிப்பு (SemVer)
------------------------------------------

இந்த ஆவணத்தில் MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", மற்றும் "OPTIONAL" ,போன்ற வார்த்தைகள், [RFC 2119](https://tools.ietf.org/html/rfc2119)இல் பொருள் குறிப்பிட்டிருப்பது போல அறிந்துகொள்ளப்பட வேண்டும்.

1. சொற்பொருள் பதிப்பைப் பயன்படுத்தும் மென்பொருள் பொது APIஐ அறிவிக்க வேண்டும். இந்த API குறியீட்டில் அறிவிக்கப்படலாம் அல்லது ஆவணத்தில் கண்டிப்பாக இருக்கலாம்.
எப்படி செய்யப்பட்டாலும், அது துல்லியமாகவும் விரிவாகவும் இருக்க வேண்டும்.

2. ஒரு சாதாரண பதிப்பு எண் X, Y மற்றும் Z இருக்கும் X.Y.Z வடிவத்தை எடுக்க வேண்டும்
எதிர்மறை அல்லாத முழு எண்கள் மற்றும் முன்னணி பூஜ்ஜியங்களைக் கொண்டிருக்கக்கூடாது. X என்பது
பெரிய பதிப்பு, Y என்பது சிறிய பதிப்பு, மற்றும் Z என்பது இணைப்பு பதிப்பு.
ஒவ்வொரு உறுப்பும் எண்ணாக அதிகரிக்க வேண்டும். உதாரணமாக: 1.9.0 -> 1.10.0 -> 1.11.0.

3. ஒரு பதிப்பு தொகுப்பு வெளியிடப்பட்டவுடன், அந்த பதிப்பின் உள்ளடக்கங்கள்
மாற்றியமைக்கக் கூடாது. எந்த மாற்றங்களும் ஒரு புதிய பதிப்பாக வெளியிடப்பட வேண்டும்.

4. முதன்மை பதிப்பு பூஜ்யம் (0.y.z) ஆரம்ப வளர்ச்சிக்கு. எந்த நேரத்திலும் 
எதையும் மாற்றலாம். பொது API நிலையானதாக கருதப்படக்கூடாது.

5. பதிப்பு 1.0.0 பொது API ஐ வரையறுக்கிறது. 
இந்த வெளியீட்டிற்குப் பிறகு பதிப்பு எண் அதிகரிக்கப்படும் விதம் இந்த பொது API மற்றும் அது எவ்வாறு மாறுகிறது என்பதைப் பொறுத்தது.

6. பேட்ச் பதிப்பு Z (x.y.Z | x> 0) மட்டுமே பின்னோக்கி இணக்கமான பிழை திருத்தங்கள் அறிமுகப்படுத்தப்பட்டால் அதிகரிக்கப்பட வேண்டும். பிழை திருத்தம் என்பது தவறான நடத்தையை சரிசெய்யும் உள் மாற்றமாக வரையறுக்கப்படுகிறது.

7. பொது APIக்கு புதிய, பின்னோக்கி இணக்கமான செயல்பாடு அறிமுகப்படுத்தப்பட்டால் மைனர் பதிப்பு Y (x.Y.z | x> 0) அதிகரிக்கப்பட வேண்டும். ஏதேனும் பொது ஏபிஐ செயல்பாடு குறைக்கப்பட்டதாகக் குறிக்கப்பட்டால் அது அதிகரிக்கப்பட வேண்டும். தனியார் குறியீட்டில் கணிசமான புதிய செயல்பாடு அல்லது மேம்பாடுகள் அறிமுகப்படுத்தப்பட்டால் அது அதிகரிக்கப்படலாம்.
 இது இணைப்பு நிலை மாற்றங்களை உள்ளடக்கியிருக்கலாம். சிறிய பதிப்பு அதிகரிக்கும் போது இணைப்பு பதிப்பு பூஜ்ஜியத்திற்கு மீட்டமைக்கப்பட வேண்டும்.

8. Major version X (X.y.z | X > 0) MUST be incremented if any backwards
incompatible changes are introduced to the public API. It MAY also include minor
and patch level changes. Patch and minor version MUST be reset to 0 when major
version is incremented.

9. A pre-release version MAY be denoted by appending a hyphen and a
series of dot separated identifiers immediately following the patch
version. Identifiers MUST comprise only ASCII alphanumerics and hyphens
[0-9A-Za-z-]. Identifiers MUST NOT be empty. Numeric identifiers MUST
NOT include leading zeroes. Pre-release versions have a lower
precedence than the associated normal version. A pre-release version
indicates that the version is unstable and might not satisfy the
intended compatibility requirements as denoted by its associated
normal version. Examples: 1.0.0-alpha, 1.0.0-alpha.1, 1.0.0-0.3.7,
1.0.0-x.7.z.92, 1.0.0-x-y-z.--.

10. Build metadata MAY be denoted by appending a plus sign and a series of dot
separated identifiers immediately following the patch or pre-release version.
Identifiers MUST comprise only ASCII alphanumerics and hyphens [0-9A-Za-z-].
Identifiers MUST NOT be empty. Build metadata MUST be ignored when determining
version precedence. Thus two versions that differ only in the build metadata,
have the same precedence. Examples: 1.0.0-alpha+001, 1.0.0+20130313144700,
1.0.0-beta+exp.sha.5114f85, 1.0.0+21AF26D3----117B344092BD.

11. Precedence refers to how versions are compared to each other when ordered.

   1. Precedence MUST be calculated by separating the version into major,
      minor, patch and pre-release identifiers in that order (Build metadata
      does not figure into precedence).

   2. Precedence is determined by the first difference when comparing each of
      these identifiers from left to right as follows: Major, minor, and patch
      versions are always compared numerically.

      Example: 1.0.0 < 2.0.0 < 2.1.0 < 2.1.1.

   3. When major, minor, and patch are equal, a pre-release version has lower
      precedence than a normal version:

      Example: 1.0.0-alpha < 1.0.0.

   4. Precedence for two pre-release versions with the same major, minor, and
      patch version MUST be determined by comparing each dot separated identifier
      from left to right until a difference is found as follows:

      1. Identifiers consisting of only digits are compared numerically.

      2. Identifiers with letters or hyphens are compared lexically in ASCII
         sort order.

      3. Numeric identifiers always have lower precedence than non-numeric
         identifiers.

      4. A larger set of pre-release fields has a higher precedence than a
         smaller set, if all of the preceding identifiers are equal.

      Example: 1.0.0-alpha < 1.0.0-alpha.1 < 1.0.0-alpha.beta < 1.0.0-beta < 
      1.0.0-beta.2 < 1.0.0-beta.11 < 1.0.0-rc.1 < 1.0.0.

Backus–Naur Form Grammar for Valid SemVer Versions
--------------------------------------------------
```
<valid semver> ::= <version core>
                 | <version core> "-" <pre-release>
                 | <version core> "+" <build>
                 | <version core> "-" <pre-release> "+" <build>

<version core> ::= <major> "." <minor> "." <patch>

<major> ::= <numeric identifier>

<minor> ::= <numeric identifier>

<patch> ::= <numeric identifier>

<pre-release> ::= <dot-separated pre-release identifiers>

<dot-separated pre-release identifiers> ::= <pre-release identifier>
                                          | <pre-release identifier> "." <dot-separated pre-release identifiers>

<build> ::= <dot-separated build identifiers>

<dot-separated build identifiers> ::= <build identifier>
                                    | <build identifier> "." <dot-separated build identifiers>

<pre-release identifier> ::= <alphanumeric identifier>
                           | <numeric identifier>

<build identifier> ::= <alphanumeric identifier>
                     | <digits>

<alphanumeric identifier> ::= <non-digit>
                            | <non-digit> <identifier characters>
                            | <identifier characters> <non-digit>
                            | <identifier characters> <non-digit> <identifier characters>

<numeric identifier> ::= "0"
                       | <positive digit>
                       | <positive digit> <digits>

<identifier characters> ::= <identifier character>
                          | <identifier character> <identifier characters>

<identifier character> ::= <digit>
                         | <non-digit>

<non-digit> ::= <letter>
              | "-"

<digits> ::= <digit>
           | <digit> <digits>

<digit> ::= "0"
          | <positive digit>

<positive digit> ::= "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"

<letter> ::= "A" | "B" | "C" | "D" | "E" | "F" | "G" | "H" | "I" | "J"
           | "K" | "L" | "M" | "N" | "O" | "P" | "Q" | "R" | "S" | "T"
           | "U" | "V" | "W" | "X" | "Y" | "Z" | "a" | "b" | "c" | "d"
           | "e" | "f" | "g" | "h" | "i" | "j" | "k" | "l" | "m" | "n"
           | "o" | "p" | "q" | "r" | "s" | "t" | "u" | "v" | "w" | "x"
           | "y" | "z"
```

Why Use Semantic Versioning?
----------------------------

This is not a new or revolutionary idea. In fact, you probably do something
close to this already. The problem is that "close" isn't good enough. Without
compliance to some sort of formal specification, version numbers are
essentially useless for dependency management. By giving a name and clear
definition to the above ideas, it becomes easy to communicate your intentions
to the users of your software. Once these intentions are clear, flexible (but
not too flexible) dependency specifications can finally be made.

A simple example will demonstrate how Semantic Versioning can make dependency
hell a thing of the past. Consider a library called "Firetruck." It requires a
Semantically Versioned package named "Ladder." At the time that Firetruck is
created, Ladder is at version 3.1.0. Since Firetruck uses some functionality
that was first introduced in 3.1.0, you can safely specify the Ladder
dependency as greater than or equal to 3.1.0 but less than 4.0.0. Now, when
Ladder version 3.1.1 and 3.2.0 become available, you can release them to your
package management system and know that they will be compatible with existing
dependent software.

As a responsible developer you will, of course, want to verify that any
package upgrades function as advertised. The real world is a messy place;
there's nothing we can do about that but be vigilant. What you can do is let
Semantic Versioning provide you with a sane way to release and upgrade
packages without having to roll new versions of dependent packages, saving you
time and hassle.

If all of this sounds desirable, all you need to do to start using Semantic
Versioning is to declare that you are doing so and then follow the rules. Link
to this website from your README so others know the rules and can benefit from
them.

FAQ
---

### How should I deal with revisions in the 0.y.z initial development phase?

The simplest thing to do is start your initial development release at 0.1.0
and then increment the minor version for each subsequent release.

### How do I know when to release 1.0.0?

If your software is being used in production, it should probably already be
1.0.0. If you have a stable API on which users have come to depend, you should
be 1.0.0. If you're worrying a lot about backwards compatibility, you should
probably already be 1.0.0.

### Doesn't this discourage rapid development and fast iteration?

Major version zero is all about rapid development. If you're changing the API
every day you should either still be in version 0.y.z or on a separate
development branch working on the next major version.

### If even the tiniest backwards incompatible changes to the public API require a major version bump, won't I end up at version 42.0.0 very rapidly?

This is a question of responsible development and foresight. Incompatible
changes should not be introduced lightly to software that has a lot of
dependent code. The cost that must be incurred to upgrade can be significant.
Having to bump major versions to release incompatible changes means you'll
think through the impact of your changes, and evaluate the cost/benefit ratio
involved.

### Documenting the entire public API is too much work!

It is your responsibility as a professional developer to properly document
software that is intended for use by others. Managing software complexity is a
hugely important part of keeping a project efficient, and that's hard to do if
nobody knows how to use your software, or what methods are safe to call. In
the long run, Semantic Versioning, and the insistence on a well defined public
API can keep everyone and everything running smoothly.

### What do I do if I accidentally release a backwards incompatible change as a minor version?

As soon as you realize that you've broken the Semantic Versioning spec, fix
the problem and release a new minor version that corrects the problem and
restores backwards compatibility. Even under this circumstance, it is
unacceptable to modify versioned releases. If it's appropriate,
document the offending version and inform your users of the problem so that
they are aware of the offending version.

### What should I do if I update my own dependencies without changing the public API?

That would be considered compatible since it does not affect the public API.
Software that explicitly depends on the same dependencies as your package
should have their own dependency specifications and the author will notice any
conflicts. Determining whether the change is a patch level or minor level
modification depends on whether you updated your dependencies in order to fix
a bug or introduce new functionality. I would usually expect additional code
for the latter instance, in which case it's obviously a minor level increment.

### What if I inadvertently alter the public API in a way that is not compliant with the version number change (i.e. the code incorrectly introduces a major breaking change in a patch release)?

Use your best judgment. If you have a huge audience that will be drastically
impacted by changing the behavior back to what the public API intended, then
it may be best to perform a major version release, even though the fix could
strictly be considered a patch release. Remember, Semantic Versioning is all
about conveying meaning by how the version number changes. If these changes
are important to your users, use the version number to inform them.

### How should I handle deprecating functionality?

Deprecating existing functionality is a normal part of software development and
is often required to make forward progress. When you deprecate part of your
public API, you should do two things: (1) update your documentation to let
users know about the change, (2) issue a new minor release with the deprecation
in place. Before you completely remove the functionality in a new major release
there should be at least one minor release that contains the deprecation so
that users can smoothly transition to the new API.

### Does SemVer have a size limit on the version string?

No, but use good judgment. A 255 character version string is probably overkill,
for example. Also, specific systems may impose their own limits on the size of
the string.

### Is "v1.2.3" a semantic version?

No, "v1.2.3" is not a semantic version. However, prefixing a semantic version
with a "v" is a common way (in English) to indicate it is a version number.
Abbreviating "version" as "v" is often seen with version control. Example:
`git tag v1.2.3 -m "Release version 1.2.3"`, in which case "v1.2.3" is a tag
name and the semantic version is "1.2.3".

### Is there a suggested regular expression (RegEx) to check a SemVer string?

There are two. One with named groups for those systems that support them
(PCRE [Perl Compatible Regular Expressions, i.e. Perl, PHP and R], Python
and Go).

See: <https://regex101.com/r/Ly7O1x/3/>

```
^(?P<major>0|[1-9]\d*)\.(?P<minor>0|[1-9]\d*)\.(?P<patch>0|[1-9]\d*)(?:-(?P<prerelease>(?:0|[1-9]\d*|\d*[a-zA-Z-][0-9a-zA-Z-]*)(?:\.(?:0|[1-9]\d*|\d*[a-zA-Z-][0-9a-zA-Z-]*))*))?(?:\+(?P<buildmetadata>[0-9a-zA-Z-]+(?:\.[0-9a-zA-Z-]+)*))?$
```

And one with numbered capture groups instead (so cg1 = major, cg2 = minor,
cg3 = patch, cg4 = prerelease and cg5 = buildmetadata) that is compatible
with ECMA Script (JavaScript), PCRE (Perl Compatible Regular Expressions,
i.e. Perl, PHP and R), Python and Go.

See: <https://regex101.com/r/vkijKf/1/>

```
^(0|[1-9]\d*)\.(0|[1-9]\d*)\.(0|[1-9]\d*)(?:-((?:0|[1-9]\d*|\d*[a-zA-Z-][0-9a-zA-Z-]*)(?:\.(?:0|[1-9]\d*|\d*[a-zA-Z-][0-9a-zA-Z-]*))*))?(?:\+([0-9a-zA-Z-]+(?:\.[0-9a-zA-Z-]+)*))?$
```

About
-----

The Semantic Versioning specification was originally authored by [Tom
Preston-Werner](https://tom.preston-werner.com), inventor of Gravatar and
cofounder of GitHub.

If you'd like to leave feedback, please [open an issue on
GitHub](https://github.com/semver/semver/issues).

License
-------

[Creative Commons ― CC BY 3.0](https://creativecommons.org/licenses/by/3.0/)

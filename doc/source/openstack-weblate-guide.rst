.. _openstack-weblate-guide:

=====================================================
Getting started with translation in OpenStack Weblate
=====================================================

Use OpenStack Weblate to find a string, translate it, and check the saved
translation. This example follows a Korean translation in the ``doc``
component of the ``i18n`` project. Choose an untranslated string to follow
along. The example string is already translated.

The numbered boxes in the screenshots show where to click and what to check.
The screenshots use the English interface of Weblate 2026.10.1.

.. contents:: On this page
   :local:
   :depth: 2

1. Open the site and sign in
----------------------------

Open `OpenStack Weblate <https://openstack.weblate.cloud/>`_. During this
walkthrough, opening the site from a signed-out session redirected directly to
the OpenInfraID sign-in page at ``https://id.openinfra.dev/auth/login``.

The sign-in page explains that OpenStackID is now called OpenInfraID and that
existing accounts can still be used. This guide assumes that you already have
an OpenInfraID account.

1. Enter your account email address in **Email Address**.
2. Click the **>** button to continue.

.. figure:: ../../resources/weblate/01-sign-in.png
   :alt: OpenInfraID sign-in page with the email field and next button
         highlighted
   :width: 100%

   **1.** Account email field. **2.** Button to continue to the password step.

The next screen prompts for your password.

1. Enter your password in **Enter Your Password**.
2. Click **Continue**.
3. After authentication, you return to the OpenStack Weblate **Dashboard**.

.. figure:: ../../resources/weblate/02-password.png
   :alt: Password field and Continue button highlighted, with the account email
         redacted
   :width: 100%

   **1.** Password field. **2.** Continue button to sign in.

.. note::

   If you are already signed in, these steps may be skipped. The password
   screenshot was taken before entering a password, so the field is empty.

2. Choose a translation project
-------------------------------

Open **Projects** in the top navigation bar and select **Browse all projects**.
The Dashboard contents depend on your account's watched projects and other
preferences. The full project list provides a starting point for new
contributors.

.. figure:: ../../resources/weblate/03-project-menu.png
   :alt: Projects menu and Browse all projects option highlighted on the
         Dashboard
   :width: 100%

   **1.** Projects menu. **2.** Browse all projects.

Scroll through the project list and click **i18n**. This guide uses the i18n
project, which contains internationalization documentation, as its example.
To work on another project, select that project instead.

.. figure:: ../../resources/weblate/04-project-list.png
   :alt: The i18n project link highlighted in the full project list
   :width: 100%

   **1.** The i18n project used in this walkthrough.

If **i18n** already appears in your Projects menu, you can open it directly.
The **Add project** or plus button is not needed to translate an existing
project.

3. Select the language and documentation component
--------------------------------------------------

In the i18n project's language list, click
**Korean (South Korea) (ko_KR)**. You may need to scroll down to find it.

.. figure:: ../../resources/weblate/05-language.png
   :alt: Korean South Korea ko_KR highlighted in the i18n language list
   :width: 100%

   **1.** Korean (South Korea) (ko_KR), the target language for this example.

On the Korean translation page, open the **Components** tab and select
**doc** under **master**. Here, ``i18n`` is the project, ``master`` is the
category shown in the navigation hierarchy, and ``doc`` is the documentation
component to translate. Other projects may have different categories and
component names.

.. figure:: ../../resources/weblate/06-components.png
   :alt: Components tab and the doc component under master highlighted
   :width: 100%

   **1.** Components tab. **2.** The doc component.

The **glossary** component contains terminology. For the example sentence in
this guide, open **doc**.

4. Open an untranslated string
------------------------------

Check that the breadcrumb reads
**i18n / master / doc / Korean (South Korea) (ko_KR)**.
On the **Translation** tab, find **Strings status** and click
**Untranslated strings** to open strings with an empty translation.

.. figure:: ../../resources/weblate/07-translation-status.png
   :alt: Target project component and language breadcrumb, and Untranslated
         strings link highlighted
   :width: 100%

   **1.** Check the project, component, and language. **2.** Open untranslated
   strings.

Common entry points include the following:

.. list-table:: String status filters
   :header-rows: 1
   :widths: 34 66

   * - Entry
     - When to use it
   * - Untranslated strings
     - Translate strings that do not yet have a translation.
   * - Unfinished strings
     - Work on untranslated strings or strings that need editing.
   * - All strings
     - Browse strings, including those already translated.
   * - Strings with any failing checks
     - Inspect strings flagged by automatic checks.

See the
`Weblate translation guide
<https://docs.weblate.org/en/weblate-2026.10.1/user/translating.html#translation-links>`_
for more about translation entry points and workflows. The account used in
this walkthrough could save translations directly. If your account can only
submit suggestions, follow the participation instructions for that project.

5. Read the source and its context
----------------------------------

In the editor, read the **English (United States)** source text first.
Enter your translation in the **Korean (South Korea) (ko_KR)** field below it.
The **String information** panel on the right shows the format and source
location. For this example, they are **rst-text** and
``../../source/infra.rst:80``.

.. figure:: ../../resources/weblate/08-editor.png
   :alt: English source text, Korean translation field, and format and source
         location highlighted
   :width: 100%

   **1.** English source. **2.** Korean translation field. **3.** Format and
   source location.

If the meaning is unclear, use **Nearby strings** below the editor to read the
surrounding text. Follow relevant terminology in **Glossary**, if available.
If you use **Automatic suggestions**, review them against the source before
saving. No related glossary entries were shown for this example.

The selected source text mentions Zanata and Chinese locale names. These are
part of the source's subject matter; the translation service used in this
guide is OpenStack Weblate. Do not replace a service name in the source with
Weblate merely because you are using Weblate to translate it.

6. Enter a translation while preserving RST syntax
--------------------------------------------------

Translate the human-readable text while preserving code, locale names, and
reStructuredText (RST) references. The following markup was preserved in this
example:

.. code-block:: rst

   ``zh-cn``
   ``zh-tw``
   ``zh-hans``
   ``zh-hant``
   :ref:`handling_horizon_projects`

For example, do not translate the ``:ref:`` role name or the reference
identifier. Keep the whitespace required by RST around inline markup,
including before Korean particles following inline code or references.
Preserve URLs, placeholders, commands, and other technical elements when
they appear in the source.

The following Korean translation was entered during this walkthrough.
Line breaks below are for readability; the translation was entered as one
paragraph in Weblate.

.. code-block:: rst

   이 작업은 horizon 관련 프로젝트에서 Zanata의 중국어 로케일(``zh-cn`` 및 ``zh-tw``)
   이름을 ``zh-hans`` 및 ``zh-hant`` 로 변경합니다. 다른 프로젝트와 문서(horizon 관련
   프로젝트의 문서 포함)에서는 ``zh-cn`` 및 ``zh-tw`` 를 그대로 사용합니다.
   자세한 내용은 :ref:`handling_horizon_projects` 를 참조하세요.

Before saving:

* Check that conditions, exceptions, and negations retain the source meaning.
* Preserve backticks, reference identifiers, URLs, and placeholders.
* Match terminology and writing style to the surrounding Korean translations.
* Use **Needs editing** for a translation that still requires work. It was
  left unchecked in this example after reviewing the translation.

7. Save the translation
-----------------------

After you enter a translation, **Unsaved changes!** appears below the field.
This means your changes have not yet been saved. In this walkthrough,
**Save and stay** was used to save the translation and inspect the result
without leaving the current string.

.. figure:: ../../resources/weblate/09-save-translation.png
   :alt: Entered Korean translation, Unsaved changes indicator, and Save and
         stay button highlighted
   :width: 100%

   **1.** Entered translation. **2.** Unsaved changes indicator. **3.** Save
   and stay.

.. list-table:: Save and navigation controls
   :header-rows: 1
   :widths: 30 70

   * - Control
     - Action
   * - Save and stay
     - Save the current translation and remain on the same string.
   * - Save and continue
     - Save the current translation and move to the next string.
   * - Skip
     - Skip the current string and move to the next one. Use a save button
       when you want to save an entered translation.

If a check reports a problem, compare the source and translation again.
For RST documentation, pay particular attention to backticks, roles,
whitespace, and link syntax. No failing check was displayed for the string
saved in this walkthrough.

8. Verify the saved translation in History
------------------------------------------

Open the string's **History** tab. In this walkthrough, the new entry showed
**Translation added**, with **Current translation** and **State: Translated**
next to the Korean text. This confirms that the translation was saved rather
than merely entered in the editor.

.. figure:: ../../resources/weblate/10-history.png
   :alt: History tab, Translation added event, and Current translation and
         State Translated labels highlighted
   :width: 100%

   **1.** History tab. **2.** Translation added event. **3.** Current
   translation and Translated state.

.. note::

   This confirms that the translation was saved in Weblate. It does not
   confirm that the change has reached the source repository or the published
   documentation site. Repository synchronization and publication were not
   verified in this walkthrough.

Use the **Copy permalink** link to return to a particular string later.
The
`example string's permalink
<https://openstack.weblate.cloud/translate/i18n/master/doc/ko_KR/?checksum=037c76b713c5302c>`_
opens the string saved in this walkthrough.

9. Continue to the next string
------------------------------

After using **Save and stay**, click the **Next** arrow in the top toolbar to
move on. This walkthrough verified that the next untranslated string opened.
When translating consecutive strings, you can use **Save and continue**.

.. figure:: ../../resources/weblate/11-next-string.png
   :alt: Updated position indicator and the next string's empty Korean
         translation field highlighted
   :width: 100%

   **1.** Position indicator after moving to the next string. **2.** Empty
   translation field.

The editor explains that search results stay fixed while you translate.
A counter such as ``1 / 51`` may therefore remain unchanged immediately after
saving a translation. To update the list to match the current filter, click
**Refresh results**, the circular arrow to the right of the query field.

For each remaining string, read the source and context, enter a translation,
review it, and save it. Before finishing your session, make sure your final
changes have been saved.

If your screen differs from this example
----------------------------------------

* **The Dashboard is empty:** Open Projects, then Browse all projects, and
  select the project directly.
* **The example string is missing from the untranslated list:** It was saved
  during this walkthrough. Choose another untranslated string. To inspect
  the saved example, use All strings or its permalink above.
* **Untranslated strings is unavailable:** Check whether any untranslated
  strings remain. Use All strings to review existing translations.
* **There is no save button, or only suggestions are allowed:** Check your
  account permissions and the project's participation instructions. The
  controls shown here reflect the account used for this walkthrough.
* **A saved string still appears in untranslated search results:** Verify the
  save in History, then click Refresh results to update the result list.

For more information about string states and context tools, see the
`official Weblate translation documentation
<https://docs.weblate.org/en/weblate-2026.10.1/user/translating.html>`_.

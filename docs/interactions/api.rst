.. currentmodule:: snakecord

Interactions API Reference
============================

The following section outlines the API of interactions, as implemented by the library.

For documentation about the rest of the library, check :doc:`/api`.

Models
--------

Similar to :ref:`snakecord_api_models`, these are not meant to be constructed by the user.

Interaction
~~~~~~~~~~~~

.. attributetable:: Interaction

.. autoclass:: Interaction()
    :members:

InteractionResponse
~~~~~~~~~~~~~~~~~~~~

.. attributetable:: InteractionResponse

.. autoclass:: InteractionResponse()
    :members:

InteractionMessage
~~~~~~~~~~~~~~~~~~~

.. attributetable:: InteractionMessage

.. autoclass:: InteractionMessage()
    :members:
    :inherited-members:

MessageInteraction
~~~~~~~~~~~~~~~~~~~

.. attributetable:: MessageInteraction

.. autoclass:: MessageInteraction()
    :members:

Component
~~~~~~~~~~

.. attributetable:: Component

.. autoclass:: Component()
    :members:

ActionRow
~~~~~~~~~~

.. attributetable:: ActionRow

.. autoclass:: ActionRow()
    :members:

Button
~~~~~~~

.. attributetable:: Button

.. autoclass:: Button()
    :members:
    :inherited-members:

SelectMenu
~~~~~~~~~~~

.. attributetable:: SelectMenu

.. autoclass:: SelectMenu()
    :members:
    :inherited-members:


TextInput
~~~~~~~~~~

.. attributetable:: TextInput

.. autoclass:: TextInput()
    :members:
    :inherited-members:

AppCommand
~~~~~~~~~~~

.. attributetable:: snakecord.app_commands.AppCommand

.. autoclass:: snakecord.app_commands.AppCommand()
    :members:

AppCommandGroup
~~~~~~~~~~~~~~~~

.. attributetable:: snakecord.app_commands.AppCommandGroup

.. autoclass:: snakecord.app_commands.AppCommandGroup()
    :members:

AppCommandChannel
~~~~~~~~~~~~~~~~~~

.. attributetable:: snakecord.app_commands.AppCommandChannel

.. autoclass:: snakecord.app_commands.AppCommandChannel()
    :members:

AppCommandThread
~~~~~~~~~~~~~~~~~

.. attributetable:: snakecord.app_commands.AppCommandThread

.. autoclass:: snakecord.app_commands.AppCommandThread()
    :members:

AppCommandPermissions
~~~~~~~~~~~~~~~~~~~~~~

.. attributetable:: snakecord.app_commands.AppCommandPermissions

.. autoclass:: snakecord.app_commands.AppCommandPermissions()
    :members:

GuildAppCommandPermissions
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. attributetable:: snakecord.app_commands.GuildAppCommandPermissions

.. autoclass:: snakecord.app_commands.GuildAppCommandPermissions()
    :members:

Argument
~~~~~~~~~~

.. attributetable:: snakecord.app_commands.Argument

.. autoclass:: snakecord.app_commands.Argument()
    :members:

AllChannels
~~~~~~~~~~~~

.. attributetable:: snakecord.app_commands.AllChannels

.. autoclass:: snakecord.app_commands.AllChannels()
    :members:

Data Classes
--------------

Similar to :ref:`snakecord_api_data`, these can be received and constructed by users.

SelectOption
~~~~~~~~~~~~~

.. attributetable:: SelectOption

.. autoclass:: SelectOption
    :members:

SelectDefaultValue
~~~~~~~~~~~~~~~~~~~

.. attributetable:: SelectDefaultValue

.. autoclass:: SelectDefaultValue
    :members:

Choice
~~~~~~~

.. attributetable:: snakecord.app_commands.Choice

.. autoclass:: snakecord.app_commands.Choice
    :members:


Enumerations
-------------

.. class:: InteractionType

    Specifies the type of :class:`Interaction`.

    .. versionadded:: 2.0

    .. attribute:: ping

        Represents Snakecord pinging to see if the interaction response server is alive.
    .. attribute:: application_command

        Represents a slash command interaction.
    .. attribute:: component

        Represents a component based interaction, i.e. using the Snakecord Bot UI Kit.
    .. attribute:: autocomplete

        Represents an auto complete interaction.
    .. attribute:: modal_submit

        Represents submission of a modal interaction.

.. class:: InteractionResponseType

    Specifies the response type for the interaction.

    .. versionadded:: 2.0

    .. attribute:: pong

        Pongs the interaction when given a ping.

        See also :meth:`InteractionResponse.pong`
    .. attribute:: channel_message

        Respond to the interaction with a message.

        See also :meth:`InteractionResponse.send_message`
    .. attribute:: deferred_channel_message

        Responds to the interaction with a message at a later time.

        See also :meth:`InteractionResponse.defer`
    .. attribute:: deferred_message_update

        Acknowledges the component interaction with a promise that
        the message will update later (though there is no need to actually update the message).

        See also :meth:`InteractionResponse.defer`
    .. attribute:: message_update

        Responds to the interaction by editing the message.

        See also :meth:`InteractionResponse.edit_message`
    .. attribute:: autocomplete_result

        Responds to the autocomplete interaction with suggested choices.

        See also :meth:`InteractionResponse.autocomplete`
    .. attribute:: modal

        Responds to the interaction with a modal.

        See also :meth:`InteractionResponse.send_modal`

.. class:: ComponentType

    Represents the component type of a component.

    .. versionadded:: 2.0

    .. attribute:: action_row

        Represents the group component which holds different components in a row.

    .. attribute:: button

        Represents a button component.

    .. attribute:: text_input

        Represents a text box component.

    .. attribute:: select

        Represents a select component.

    .. attribute:: string_select

        An alias to :attr:`select`. Represents a default select component.

    .. attribute:: user_select

        Represents a user select component.

    .. attribute:: role_select

        Represents a role select component.

    .. attribute:: mentionable_select

        Represents a select in which both users and roles can be selected.

.. class:: ButtonStyle

    Represents the style of the button component.

    .. versionadded:: 2.0

    .. attribute:: primary

        Represents a blurple button for the primary action.
    .. attribute:: secondary

        Represents a grey button for the secondary action.
    .. attribute:: success

        Represents a green button for a successful action.
    .. attribute:: danger

        Represents a red button for a dangerous action.
    .. attribute:: link

        Represents a link button.

    .. attribute:: blurple

        An alias for :attr:`primary`.
    .. attribute:: grey

        An alias for :attr:`secondary`.
    .. attribute:: gray

        An alias for :attr:`secondary`.
    .. attribute:: green

        An alias for :attr:`success`.
    .. attribute:: red

        An alias for :attr:`danger`.
    .. attribute:: url

        An alias for :attr:`link`.

.. class:: TextStyle

    Represents the style of the text box component.

    .. versionadded:: 2.0

    .. attribute:: short

        Represents a short text box.
    .. attribute:: paragraph

        Represents a long form text box.
    .. attribute:: long

        An alias for :attr:`paragraph`.

.. class:: AppCommandOptionType

    The application command's option type. This is usually the type of parameter an application command takes.

    .. versionadded:: 2.0

    .. attribute:: subcommand

        A subcommand.
    .. attribute:: subcommand_group

        A subcommand group.
    .. attribute:: string

        A string parameter.
    .. attribute:: integer

        A integer parameter.
    .. attribute:: boolean

        A boolean parameter.
    .. attribute:: user

        A user parameter.
    .. attribute:: channel

        A channel parameter.
    .. attribute:: role

        A role parameter.
    .. attribute:: mentionable

        A mentionable parameter.
    .. attribute:: number

        A number parameter.
    .. attribute:: attachment

        An attachment parameter.

.. class:: AppCommandType

    The type of application command.

    .. versionadded:: 2.0

    .. attribute:: chat_input

        A slash command.
    .. attribute:: user

        A user context menu command.
    .. attribute:: message

        A message context menu command.

.. class:: AppCommandPermissionType

    The application command's permission type.

    .. versionadded:: 2.0

    .. attribute:: role

        The permission is for a role.
    .. attribute:: channel

        The permission is for one or all channels.
    .. attribute:: user

        The permission is for a user.

.. _snakecord_ui_kit:

Bot UI Kit
-------------

The library has helpers to aid in creating component-based UIs. These are all in the ``snakecord.ui`` package.


View
~~~~~~~

.. attributetable:: snakecord.ui.View

.. autoclass:: snakecord.ui.View
    :members:

Modal
~~~~~~

.. attributetable:: snakecord.ui.Modal

.. autoclass:: snakecord.ui.Modal
    :members:
    :inherited-members:

Item
~~~~~~~

.. attributetable:: snakecord.ui.Item

.. autoclass:: snakecord.ui.Item
    :members:

DynamicItem
~~~~~~~~~~~~

.. attributetable:: snakecord.ui.DynamicItem

.. autoclass:: snakecord.ui.DynamicItem
    :members:
    :inherited-members:

Button
~~~~~~~

.. attributetable:: snakecord.ui.Button

.. autoclass:: snakecord.ui.Button
    :members:
    :inherited-members:

.. autofunction:: snakecord.ui.button
    :decorator:

Select Menus
~~~~~~~~~~~~~

The library provides classes to help create the different types of select menus.

Select
+++++++

.. attributetable:: snakecord.ui.Select

.. autoclass:: snakecord.ui.Select
    :members:
    :inherited-members:

ChannelSelect
++++++++++++++

.. attributetable:: snakecord.ui.ChannelSelect

.. autoclass:: snakecord.ui.ChannelSelect
    :members:
    :inherited-members:

RoleSelect
++++++++++

.. attributetable:: snakecord.ui.RoleSelect

.. autoclass:: snakecord.ui.RoleSelect
    :members:
    :inherited-members:

MentionableSelect
++++++++++++++++++

.. attributetable:: snakecord.ui.MentionableSelect

.. autoclass:: snakecord.ui.MentionableSelect
    :members:
    :inherited-members:

UserSelect
+++++++++++

.. attributetable:: snakecord.ui.UserSelect

.. autoclass:: snakecord.ui.UserSelect
    :members:
    :inherited-members:

select
+++++++
.. autofunction:: snakecord.ui.select
    :decorator:


TextInput
~~~~~~~~~~~

.. attributetable:: snakecord.ui.TextInput

.. autoclass:: snakecord.ui.TextInput
    :members:
    :inherited-members:

.. _snakecord_app_commands:

Application Commands
----------------------

The library has helpers to aid in creation of application commands. These are all in the ``snakecord.app_commands`` package.

CommandTree
~~~~~~~~~~~~

.. attributetable:: snakecord.app_commands.CommandTree

.. autoclass:: snakecord.app_commands.CommandTree
    :members:
    :exclude-members: error, command, context_menu

    .. automethod:: CommandTree.command(*, name=..., description=..., nsfw=False, guild=..., guilds=..., auto_locale_strings=True, extras=...)
        :decorator:

    .. automethod:: CommandTree.context_menu(*, name=..., nsfw=False, guild=..., guilds=..., auto_locale_strings=True, extras=...)
        :decorator:

    .. automethod:: CommandTree.error(coro)
        :decorator:

Commands
~~~~~~~~~

Command
++++++++

.. attributetable:: snakecord.app_commands.Command

.. autoclass:: snakecord.app_commands.Command
    :members:
    :exclude-members: error, autocomplete

    .. automethod:: Command.autocomplete(name)
        :decorator:

    .. automethod:: Command.error(coro)
        :decorator:

Parameter
++++++++++

.. attributetable:: snakecord.app_commands.Parameter

.. autoclass:: snakecord.app_commands.Parameter()
    :members:

ContextMenu
++++++++++++

.. attributetable:: snakecord.app_commands.ContextMenu

.. autoclass:: snakecord.app_commands.ContextMenu
    :members:
    :exclude-members: error

    .. automethod:: ContextMenu.error(coro)
        :decorator:

Group
++++++

.. attributetable:: snakecord.app_commands.Group

.. autoclass:: snakecord.app_commands.Group
    :members:
    :exclude-members: error, command

    .. automethod:: Group.command(*, name=..., description=..., nsfw=False, auto_locale_strings=True, extras=...)
        :decorator:

    .. automethod:: Group.error(coro)
        :decorator:

Decorators
~~~~~~~~~~~

.. autofunction:: snakecord.app_commands.command
    :decorator:

.. autofunction:: snakecord.app_commands.context_menu
    :decorator:

.. autofunction:: snakecord.app_commands.describe
    :decorator:

.. autofunction:: snakecord.app_commands.rename
    :decorator:

.. autofunction:: snakecord.app_commands.choices
    :decorator:

.. autofunction:: snakecord.app_commands.autocomplete
    :decorator:

.. autofunction:: snakecord.app_commands.guilds
    :decorator:

.. autofunction:: snakecord.app_commands.guild_only
    :decorator:

.. autofunction:: snakecord.app_commands.default_permissions
    :decorator:

Checks
~~~~~~~

.. autofunction:: snakecord.app_commands.check
    :decorator:

.. autofunction:: snakecord.app_commands.checks.has_role
    :decorator:

.. autofunction:: snakecord.app_commands.checks.has_any_role
    :decorator:

.. autofunction:: snakecord.app_commands.checks.has_permissions
    :decorator:

.. autofunction:: snakecord.app_commands.checks.bot_has_permissions
    :decorator:

.. autofunction:: snakecord.app_commands.checks.cooldown
    :decorator:

.. autofunction:: snakecord.app_commands.checks.dynamic_cooldown
    :decorator:

Cooldown
~~~~~~~~~

.. attributetable:: snakecord.app_commands.Cooldown

.. autoclass:: snakecord.app_commands.Cooldown
    :members:


Namespace
~~~~~~~~~~

.. attributetable:: snakecord.app_commands.Namespace

.. autoclass:: snakecord.app_commands.Namespace()
    :members:

Transformers
~~~~~~~~~~~~~

Transformer
++++++++++++

.. attributetable:: snakecord.app_commands.Transformer

.. autoclass:: snakecord.app_commands.Transformer
    :members:

Transform
++++++++++

.. attributetable:: snakecord.app_commands.Transform

.. autoclass:: snakecord.app_commands.Transform
    :members:

Range
++++++

.. attributetable:: snakecord.app_commands.Range

.. autoclass:: snakecord.app_commands.Range
    :members:

Translations
~~~~~~~~~~~~~

Translator
+++++++++++

.. attributetable:: snakecord.app_commands.Translator

.. autoclass:: snakecord.app_commands.Translator
    :members:

locale_str
+++++++++++

.. attributetable:: snakecord.app_commands.locale_str

.. autoclass:: snakecord.app_commands.locale_str
    :members:

TranslationContext
+++++++++++++++++++

.. attributetable:: snakecord.app_commands.TranslationContext

.. autoclass:: snakecord.app_commands.TranslationContext
    :members:

TranslationContextLocation
+++++++++++++++++++++++++++

.. class:: TranslationContextLocation
    :module: snakecord.app_commands

    An enum representing the location context that the translation occurs in when requested for translation.

    .. versionadded:: 2.0

    .. attribute:: command_name

        The translation involved a command name.
    .. attribute:: command_description

        The translation involved a command description.

    .. attribute:: group_name

        The translation involved a group name.
    .. attribute:: group_description

        The translation involved a group description.
    .. attribute:: parameter_name

        The translation involved a parameter name.
    .. attribute:: parameter_description

        The translation involved a parameter description.
    .. attribute:: choice_name

        The translation involved a choice name.
    .. attribute:: other

        The translation involved something else entirely. This is useful for running
        :meth:`Translator.translate` for custom usage.

Exceptions
~~~~~~~~~~~

.. autoexception:: snakecord.app_commands.AppCommandError
    :members:

.. autoexception:: snakecord.app_commands.CommandInvokeError
    :members:

.. autoexception:: snakecord.app_commands.TransformerError
    :members:

.. autoexception:: snakecord.app_commands.TranslationError
    :members:

.. autoexception:: snakecord.app_commands.CheckFailure
    :members:

.. autoexception:: snakecord.app_commands.NoPrivateMessage
    :members:

.. autoexception:: snakecord.app_commands.MissingRole
    :members:

.. autoexception:: snakecord.app_commands.MissingAnyRole
    :members:

.. autoexception:: snakecord.app_commands.MissingPermissions
    :members:

.. autoexception:: snakecord.app_commands.BotMissingPermissions
    :members:

.. autoexception:: snakecord.app_commands.CommandOnCooldown
    :members:

.. autoexception:: snakecord.app_commands.CommandLimitReached
    :members:

.. autoexception:: snakecord.app_commands.CommandAlreadyRegistered
    :members:

.. autoexception:: snakecord.app_commands.CommandSignatureMismatch
    :members:

.. autoexception:: snakecord.app_commands.CommandNotFound
    :members:

.. autoexception:: snakecord.app_commands.MissingApplicationID
    :members:

.. autoexception:: snakecord.app_commands.CommandSyncFailure
    :members:

Exception Hierarchy
++++++++++++++++++++

.. exception_hierarchy::

    - :exc:`~snakecord.SnakecordException`
        - :exc:`~snakecord.app_commands.AppCommandError`
            - :exc:`~snakecord.app_commands.CommandInvokeError`
            - :exc:`~snakecord.app_commands.TransformerError`
            - :exc:`~snakecord.app_commands.TranslationError`
            - :exc:`~snakecord.app_commands.CheckFailure`
                - :exc:`~snakecord.app_commands.NoPrivateMessage`
                - :exc:`~snakecord.app_commands.MissingRole`
                - :exc:`~snakecord.app_commands.MissingAnyRole`
                - :exc:`~snakecord.app_commands.MissingPermissions`
                - :exc:`~snakecord.app_commands.BotMissingPermissions`
                - :exc:`~snakecord.app_commands.CommandOnCooldown`
            - :exc:`~snakecord.app_commands.CommandLimitReached`
            - :exc:`~snakecord.app_commands.CommandAlreadyRegistered`
            - :exc:`~snakecord.app_commands.CommandSignatureMismatch`
            - :exc:`~snakecord.app_commands.CommandNotFound`
            - :exc:`~snakecord.app_commands.MissingApplicationID`
            - :exc:`~snakecord.app_commands.CommandSyncFailure`
        - :exc:`~snakecord.HTTPException`
            - :exc:`~snakecord.app_commands.CommandSyncFailure`
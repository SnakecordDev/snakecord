.. currentmodule:: snakecord

API Reference
===============

The following section outlines the API of snakecord's command extension module.

.. _ext_commands_api_bot:

Bots
------

Bot
~~~~

.. attributetable:: snakecord.ext.commands.Bot

.. autoclass:: snakecord.ext.commands.Bot
    :members:
    :inherited-members:
    :exclude-members: after_invoke, before_invoke, check, check_once, command, event, group, hybrid_command, hybrid_group, listen

    .. automethod:: Bot.after_invoke()
        :decorator:

    .. automethod:: Bot.before_invoke()
        :decorator:

    .. automethod:: Bot.check()
        :decorator:

    .. automethod:: Bot.check_once()
        :decorator:

    .. automethod:: Bot.command(*args, **kwargs)
        :decorator:

    .. automethod:: Bot.event()
        :decorator:

    .. automethod:: Bot.group(*args, **kwargs)
        :decorator:

    .. automethod:: Bot.hybrid_command(name=..., with_app_command=True, *args, **kwargs)
        :decorator:

    .. automethod:: Bot.hybrid_group(name=..., with_app_command=True, *args, **kwargs)
        :decorator:

    .. automethod:: Bot.listen(name=None)
        :decorator:

AutoShardedBot
~~~~~~~~~~~~~~~~

.. attributetable:: snakecord.ext.commands.AutoShardedBot

.. autoclass:: snakecord.ext.commands.AutoShardedBot
    :members:

Prefix Helpers
----------------

.. autofunction:: snakecord.ext.commands.when_mentioned

.. autofunction:: snakecord.ext.commands.when_mentioned_or

.. _ext_commands_api_events:

Event Reference
-----------------

These events function similar to :ref:`the regular events <snakecord-api-events>`, except they
are custom to the command extension module.

.. function:: snakecord.ext.commands.on_command_error(ctx, error)

    An error handler that is called when an error is raised
    inside a command either through user input error, check
    failure, or an error in your own code.

    A default one is provided (:meth:`.Bot.on_command_error`).

    :param ctx: The invocation context.
    :type ctx: :class:`.Context`
    :param error: The error that was raised.
    :type error: :class:`.CommandError` derived

.. function:: snakecord.ext.commands.on_command(ctx)

    An event that is called when a command is found and is about to be invoked.

    This event is called regardless of whether the command itself succeeds via
    error or completes.

    :param ctx: The invocation context.
    :type ctx: :class:`.Context`

.. function:: snakecord.ext.commands.on_command_completion(ctx)

    An event that is called when a command has completed its invocation.

    This event is called only if the command succeeded, i.e. all checks have
    passed and the user input it correctly.

    :param ctx: The invocation context.
    :type ctx: :class:`.Context`

.. _ext_commands_api_command:

Commands
----------

Decorators
~~~~~~~~~~~~

.. autofunction:: snakecord.ext.commands.command
    :decorator:

.. autofunction:: snakecord.ext.commands.group
    :decorator:

.. autofunction:: snakecord.ext.commands.hybrid_command
    :decorator:

.. autofunction:: snakecord.ext.commands.hybrid_group
    :decorator:


Command
~~~~~~~~~

.. attributetable:: snakecord.ext.commands.Command

.. autoclass:: snakecord.ext.commands.Command
    :members:
    :special-members: __call__
    :exclude-members: after_invoke, before_invoke, error

    .. automethod:: Command.after_invoke()
        :decorator:

    .. automethod:: Command.before_invoke()
        :decorator:

    .. automethod:: Command.error()
        :decorator:

Group
~~~~~~

.. attributetable:: snakecord.ext.commands.Group

.. autoclass:: snakecord.ext.commands.Group
    :members:
    :inherited-members:
    :exclude-members: after_invoke, before_invoke, command, error, group

    .. automethod:: Group.after_invoke()
        :decorator:

    .. automethod:: Group.before_invoke()
        :decorator:

    .. automethod:: Group.command(*args, **kwargs)
        :decorator:

    .. automethod:: Group.error()
        :decorator:

    .. automethod:: Group.group(*args, **kwargs)
        :decorator:

GroupMixin
~~~~~~~~~~~

.. attributetable:: snakecord.ext.commands.GroupMixin

.. autoclass:: snakecord.ext.commands.GroupMixin
    :members:
    :exclude-members: command, group

    .. automethod:: GroupMixin.command(*args, **kwargs)
        :decorator:

    .. automethod:: GroupMixin.group(*args, **kwargs)
        :decorator:

HybridCommand
~~~~~~~~~~~~~~

.. attributetable:: snakecord.ext.commands.HybridCommand

.. autoclass:: snakecord.ext.commands.HybridCommand
    :members:
    :special-members: __call__
    :exclude-members: after_invoke, autocomplete, before_invoke, error

    .. automethod:: HybridCommand.after_invoke()
        :decorator:

    .. automethod:: HybridCommand.autocomplete(name)
        :decorator:

    .. automethod:: HybridCommand.before_invoke()
        :decorator:

    .. automethod:: HybridCommand.error()
        :decorator:

HybridGroup
~~~~~~~~~~~~

.. attributetable:: snakecord.ext.commands.HybridGroup

.. autoclass:: snakecord.ext.commands.HybridGroup
    :members:
    :inherited-members:
    :exclude-members: after_invoke, autocomplete, before_invoke, command, error, group

    .. automethod:: HybridGroup.after_invoke()
        :decorator:

    .. automethod:: HybridGroup.autocomplete(name)
        :decorator:

    .. automethod:: HybridGroup.before_invoke()
        :decorator:

    .. automethod:: HybridGroup.command(*args, **kwargs)
        :decorator:

    .. automethod:: HybridGroup.error()
        :decorator:

    .. automethod:: HybridGroup.group(*args, **kwargs)
        :decorator:


.. _ext_commands_api_cogs:

Cogs
------

Cog
~~~~

.. attributetable:: snakecord.ext.commands.Cog

.. autoclass:: snakecord.ext.commands.Cog
    :members:

GroupCog
~~~~~~~~~

.. attributetable:: snakecord.ext.commands.GroupCog

.. autoclass:: snakecord.ext.commands.GroupCog
    :members: interaction_check


CogMeta
~~~~~~~~

.. attributetable:: snakecord.ext.commands.CogMeta

.. autoclass:: snakecord.ext.commands.CogMeta
    :members:

.. _ext_commands_help_command:

Help Commands
---------------

HelpCommand
~~~~~~~~~~~~

.. attributetable:: snakecord.ext.commands.HelpCommand

.. autoclass:: snakecord.ext.commands.HelpCommand
    :members:

DefaultHelpCommand
~~~~~~~~~~~~~~~~~~~

.. attributetable:: snakecord.ext.commands.DefaultHelpCommand

.. autoclass:: snakecord.ext.commands.DefaultHelpCommand
    :members:
    :exclude-members: send_bot_help, send_cog_help, send_group_help, send_command_help, prepare_help_command

MinimalHelpCommand
~~~~~~~~~~~~~~~~~~~

.. attributetable:: snakecord.ext.commands.MinimalHelpCommand

.. autoclass:: snakecord.ext.commands.MinimalHelpCommand
    :members:
    :exclude-members: send_bot_help, send_cog_help, send_group_help, send_command_help, prepare_help_command

Paginator
~~~~~~~~~~

.. attributetable:: snakecord.ext.commands.Paginator

.. autoclass:: snakecord.ext.commands.Paginator
    :members:

Enums
------

.. class:: BucketType
    :module: snakecord.ext.commands

    Specifies a type of bucket for, e.g. a cooldown.

    .. attribute:: default

        The default bucket operates on a global basis.
    .. attribute:: user

        The user bucket operates on a per-user basis.
    .. attribute:: guild

        The guild bucket operates on a per-guild basis.
    .. attribute:: channel

        The channel bucket operates on a per-channel basis.
    .. attribute:: member

        The member bucket operates on a per-member basis.
    .. attribute:: category

        The category bucket operates on a per-category basis.
    .. attribute:: role

        The role bucket operates on a per-role basis.

        .. versionadded:: 1.3


.. _ext_commands_api_checks:

Checks
-------

.. autofunction:: snakecord.ext.commands.check(predicate)
    :decorator:

.. autofunction:: snakecord.ext.commands.check_any(*checks)
    :decorator:

.. autofunction:: snakecord.ext.commands.has_role(item)
    :decorator:

.. autofunction:: snakecord.ext.commands.has_permissions(**perms)
    :decorator:

.. autofunction:: snakecord.ext.commands.has_guild_permissions(**perms)
    :decorator:

.. autofunction:: snakecord.ext.commands.has_any_role(*items)
    :decorator:

.. autofunction:: snakecord.ext.commands.bot_has_role(item)
    :decorator:

.. autofunction:: snakecord.ext.commands.bot_has_permissions(**perms)
    :decorator:

.. autofunction:: snakecord.ext.commands.bot_has_guild_permissions(**perms)
    :decorator:

.. autofunction:: snakecord.ext.commands.bot_has_any_role(*items)
    :decorator:

.. autofunction:: snakecord.ext.commands.cooldown(rate, per, type=snakecord.ext.commands.BucketType.default)
    :decorator:

.. autofunction:: snakecord.ext.commands.dynamic_cooldown(cooldown, type)
    :decorator:

.. autofunction:: snakecord.ext.commands.max_concurrency(number, per=snakecord.ext.commands.BucketType.default, *, wait=False)
    :decorator:

.. autofunction:: snakecord.ext.commands.before_invoke(coro)
    :decorator:

.. autofunction:: snakecord.ext.commands.after_invoke(coro)
    :decorator:

.. autofunction:: snakecord.ext.commands.guild_only(,)
    :decorator:

.. autofunction:: snakecord.ext.commands.dm_only(,)
    :decorator:

.. autofunction:: snakecord.ext.commands.is_owner(,)
    :decorator:

.. autofunction:: snakecord.ext.commands.is_nsfw(,)
    :decorator:

.. _ext_commands_api_context:

Context
--------

.. attributetable:: snakecord.ext.commands.Context

.. autoclass:: snakecord.ext.commands.Context
    :members:
    :inherited-members:
    :exclude-members: typing

    .. automethod:: snakecord.ext.commands.Context.typing
        :async-with:

.. _ext_commands_api_converters:

Converters
------------

.. attributetable:: snakecord.ext.commands.Converter

.. autoclass:: snakecord.ext.commands.Converter
    :members:

.. attributetable:: snakecord.ext.commands.ObjectConverter

.. autoclass:: snakecord.ext.commands.ObjectConverter
    :members:

.. attributetable:: snakecord.ext.commands.MemberConverter

.. autoclass:: snakecord.ext.commands.MemberConverter
    :members:

.. attributetable:: snakecord.ext.commands.UserConverter

.. autoclass:: snakecord.ext.commands.UserConverter
    :members:

.. attributetable:: snakecord.ext.commands.MessageConverter

.. autoclass:: snakecord.ext.commands.MessageConverter
    :members:

.. attributetable:: snakecord.ext.commands.PartialMessageConverter

.. autoclass:: snakecord.ext.commands.PartialMessageConverter
    :members:

.. attributetable:: snakecord.ext.commands.GuildChannelConverter

.. autoclass:: snakecord.ext.commands.GuildChannelConverter
    :members:

.. attributetable:: snakecord.ext.commands.TextChannelConverter

.. autoclass:: snakecord.ext.commands.TextChannelConverter
    :members:

.. attributetable:: snakecord.ext.commands.VoiceChannelConverter

.. autoclass:: snakecord.ext.commands.VoiceChannelConverter
    :members:

.. attributetable:: snakecord.ext.commands.StageChannelConverter

.. autoclass:: snakecord.ext.commands.StageChannelConverter
    :members:

.. attributetable:: snakecord.ext.commands.CategoryChannelConverter

.. autoclass:: snakecord.ext.commands.CategoryChannelConverter
    :members:

.. attributetable:: snakecord.ext.commands.ForumChannelConverter

.. autoclass:: snakecord.ext.commands.ForumChannelConverter
    :members:

.. attributetable:: snakecord.ext.commands.InviteConverter

.. autoclass:: snakecord.ext.commands.InviteConverter
    :members:

.. attributetable:: snakecord.ext.commands.GuildConverter

.. autoclass:: snakecord.ext.commands.GuildConverter
    :members:

.. attributetable:: snakecord.ext.commands.RoleConverter

.. autoclass:: snakecord.ext.commands.RoleConverter
    :members:

.. attributetable:: snakecord.ext.commands.GameConverter

.. autoclass:: snakecord.ext.commands.GameConverter
    :members:

.. attributetable:: snakecord.ext.commands.ColourConverter

.. autoclass:: snakecord.ext.commands.ColourConverter
    :members:

.. attributetable:: snakecord.ext.commands.EmojiConverter

.. autoclass:: snakecord.ext.commands.EmojiConverter
    :members:

.. attributetable:: snakecord.ext.commands.PartialEmojiConverter

.. autoclass:: snakecord.ext.commands.PartialEmojiConverter
    :members:

.. attributetable:: snakecord.ext.commands.ThreadConverter

.. autoclass:: snakecord.ext.commands.ThreadConverter
    :members:

.. attributetable:: snakecord.ext.commands.GuildStickerConverter

.. autoclass:: snakecord.ext.commands.GuildStickerConverter
    :members:

.. attributetable:: snakecord.ext.commands.ScheduledEventConverter

.. autoclass:: snakecord.ext.commands.ScheduledEventConverter
    :members:

.. attributetable:: snakecord.ext.commands.clean_content

.. autoclass:: snakecord.ext.commands.clean_content
    :members:

.. attributetable:: snakecord.ext.commands.Greedy

.. autoclass:: snakecord.ext.commands.Greedy()

.. attributetable:: snakecord.ext.commands.Range

.. autoclass:: snakecord.ext.commands.Range()

.. autofunction:: snakecord.ext.commands.run_converters

Flag Converter
~~~~~~~~~~~~~~~

.. attributetable:: snakecord.ext.commands.FlagConverter

.. autoclass:: snakecord.ext.commands.FlagConverter
    :members:

.. attributetable:: snakecord.ext.commands.Flag

.. autoclass:: snakecord.ext.commands.Flag()
    :members:

.. autofunction:: snakecord.ext.commands.flag


Defaults
--------

.. attributetable:: snakecord.ext.commands.Parameter

.. autoclass:: snakecord.ext.commands.Parameter()
    :members:

.. autofunction:: snakecord.ext.commands.parameter

.. autofunction:: snakecord.ext.commands.param

.. data:: snakecord.ext.commands.Author

    A default :class:`Parameter` which returns the :attr:`~.Context.author` for this context.

    .. versionadded:: 2.0

.. data:: snakecord.ext.commands.CurrentChannel

    A default :class:`Parameter` which returns the :attr:`~.Context.channel` for this context.

    .. versionadded:: 2.0

.. data:: snakecord.ext.commands.CurrentGuild

    A default :class:`Parameter` which returns the :attr:`~.Context.guild` for this context. This will never be ``None``. If the command is called in a DM context then :exc:`~snakecord.ext.commands.NoPrivateMessage` is raised to the error handlers.

    .. versionadded:: 2.0

.. _ext_commands_api_errors:

Exceptions
-----------

.. autoexception:: snakecord.ext.commands.CommandError
    :members:

.. autoexception:: snakecord.ext.commands.ConversionError
    :members:

.. autoexception:: snakecord.ext.commands.MissingRequiredArgument
    :members:

.. autoexception:: snakecord.ext.commands.MissingRequiredAttachment
    :members:

.. autoexception:: snakecord.ext.commands.ArgumentParsingError
    :members:

.. autoexception:: snakecord.ext.commands.UnexpectedQuoteError
    :members:

.. autoexception:: snakecord.ext.commands.InvalidEndOfQuotedStringError
    :members:

.. autoexception:: snakecord.ext.commands.ExpectedClosingQuoteError
    :members:

.. autoexception:: snakecord.ext.commands.BadArgument
    :members:

.. autoexception:: snakecord.ext.commands.BadUnionArgument
    :members:

.. autoexception:: snakecord.ext.commands.BadLiteralArgument
    :members:

.. autoexception:: snakecord.ext.commands.PrivateMessageOnly
    :members:

.. autoexception:: snakecord.ext.commands.NoPrivateMessage
    :members:

.. autoexception:: snakecord.ext.commands.CheckFailure
    :members:

.. autoexception:: snakecord.ext.commands.CheckAnyFailure
    :members:

.. autoexception:: snakecord.ext.commands.CommandNotFound
    :members:

.. autoexception:: snakecord.ext.commands.DisabledCommand
    :members:

.. autoexception:: snakecord.ext.commands.CommandInvokeError
    :members:

.. autoexception:: snakecord.ext.commands.TooManyArguments
    :members:

.. autoexception:: snakecord.ext.commands.UserInputError
    :members:

.. autoexception:: snakecord.ext.commands.CommandOnCooldown
    :members:

.. autoexception:: snakecord.ext.commands.MaxConcurrencyReached
    :members:

.. autoexception:: snakecord.ext.commands.NotOwner
    :members:

.. autoexception:: snakecord.ext.commands.MessageNotFound
    :members:

.. autoexception:: snakecord.ext.commands.MemberNotFound
    :members:

.. autoexception:: snakecord.ext.commands.GuildNotFound
    :members:

.. autoexception:: snakecord.ext.commands.UserNotFound
    :members:

.. autoexception:: snakecord.ext.commands.ChannelNotFound
    :members:

.. autoexception:: snakecord.ext.commands.ChannelNotReadable
    :members:

.. autoexception:: snakecord.ext.commands.ThreadNotFound
    :members:

.. autoexception:: snakecord.ext.commands.BadColourArgument
    :members:

.. autoexception:: snakecord.ext.commands.RoleNotFound
    :members:

.. autoexception:: snakecord.ext.commands.BadInviteArgument
    :members:

.. autoexception:: snakecord.ext.commands.EmojiNotFound
    :members:

.. autoexception:: snakecord.ext.commands.PartialEmojiConversionFailure
    :members:

.. autoexception:: snakecord.ext.commands.GuildStickerNotFound
    :members:

.. autoexception:: snakecord.ext.commands.ScheduledEventNotFound
    :members:

.. autoexception:: snakecord.ext.commands.BadBoolArgument
    :members:

.. autoexception:: snakecord.ext.commands.RangeError
    :members:

.. autoexception:: snakecord.ext.commands.MissingPermissions
    :members:

.. autoexception:: snakecord.ext.commands.BotMissingPermissions
    :members:

.. autoexception:: snakecord.ext.commands.MissingRole
    :members:

.. autoexception:: snakecord.ext.commands.BotMissingRole
    :members:

.. autoexception:: snakecord.ext.commands.MissingAnyRole
    :members:

.. autoexception:: snakecord.ext.commands.BotMissingAnyRole
    :members:

.. autoexception:: snakecord.ext.commands.NSFWChannelRequired
    :members:

.. autoexception:: snakecord.ext.commands.FlagError
    :members:

.. autoexception:: snakecord.ext.commands.BadFlagArgument
    :members:

.. autoexception:: snakecord.ext.commands.MissingFlagArgument
    :members:

.. autoexception:: snakecord.ext.commands.TooManyFlags
    :members:

.. autoexception:: snakecord.ext.commands.MissingRequiredFlag
    :members:

.. autoexception:: snakecord.ext.commands.ExtensionError
    :members:

.. autoexception:: snakecord.ext.commands.ExtensionAlreadyLoaded
    :members:

.. autoexception:: snakecord.ext.commands.ExtensionNotLoaded
    :members:

.. autoexception:: snakecord.ext.commands.NoEntryPointError
    :members:

.. autoexception:: snakecord.ext.commands.ExtensionFailed
    :members:

.. autoexception:: snakecord.ext.commands.ExtensionNotFound
    :members:

.. autoexception:: snakecord.ext.commands.CommandRegistrationError
    :members:

.. autoexception:: snakecord.ext.commands.HybridCommandError
    :members:


Exception Hierarchy
~~~~~~~~~~~~~~~~~~~~~

.. exception_hierarchy::

    - :exc:`~.SnakecordException`
        - :exc:`~.commands.CommandError`
            - :exc:`~.commands.ConversionError`
            - :exc:`~.commands.UserInputError`
                - :exc:`~.commands.MissingRequiredArgument`
                - :exc:`~.commands.MissingRequiredAttachment`
                - :exc:`~.commands.TooManyArguments`
                - :exc:`~.commands.BadArgument`
                    - :exc:`~.commands.MessageNotFound`
                    - :exc:`~.commands.MemberNotFound`
                    - :exc:`~.commands.GuildNotFound`
                    - :exc:`~.commands.UserNotFound`
                    - :exc:`~.commands.ChannelNotFound`
                    - :exc:`~.commands.ChannelNotReadable`
                    - :exc:`~.commands.BadColourArgument`
                    - :exc:`~.commands.RoleNotFound`
                    - :exc:`~.commands.BadInviteArgument`
                    - :exc:`~.commands.EmojiNotFound`
                    - :exc:`~.commands.GuildStickerNotFound`
                    - :exc:`~.commands.ScheduledEventNotFound`
                    - :exc:`~.commands.PartialEmojiConversionFailure`
                    - :exc:`~.commands.BadBoolArgument`
                    - :exc:`~.commands.RangeError`
                    - :exc:`~.commands.ThreadNotFound`
                    - :exc:`~.commands.FlagError`
                        - :exc:`~.commands.BadFlagArgument`
                        - :exc:`~.commands.MissingFlagArgument`
                        - :exc:`~.commands.TooManyFlags`
                        - :exc:`~.commands.MissingRequiredFlag`
                - :exc:`~.commands.BadUnionArgument`
                - :exc:`~.commands.BadLiteralArgument`
                - :exc:`~.commands.ArgumentParsingError`
                    - :exc:`~.commands.UnexpectedQuoteError`
                    - :exc:`~.commands.InvalidEndOfQuotedStringError`
                    - :exc:`~.commands.ExpectedClosingQuoteError`
            - :exc:`~.commands.CommandNotFound`
            - :exc:`~.commands.CheckFailure`
                - :exc:`~.commands.CheckAnyFailure`
                - :exc:`~.commands.PrivateMessageOnly`
                - :exc:`~.commands.NoPrivateMessage`
                - :exc:`~.commands.NotOwner`
                - :exc:`~.commands.MissingPermissions`
                - :exc:`~.commands.BotMissingPermissions`
                - :exc:`~.commands.MissingRole`
                - :exc:`~.commands.BotMissingRole`
                - :exc:`~.commands.MissingAnyRole`
                - :exc:`~.commands.BotMissingAnyRole`
                - :exc:`~.commands.NSFWChannelRequired`
            - :exc:`~.commands.DisabledCommand`
            - :exc:`~.commands.CommandInvokeError`
            - :exc:`~.commands.CommandOnCooldown`
            - :exc:`~.commands.MaxConcurrencyReached`
            - :exc:`~.commands.HybridCommandError`
        - :exc:`~.commands.ExtensionError`
            - :exc:`~.commands.ExtensionAlreadyLoaded`
            - :exc:`~.commands.ExtensionNotLoaded`
            - :exc:`~.commands.NoEntryPointError`
            - :exc:`~.commands.ExtensionFailed`
            - :exc:`~.commands.ExtensionNotFound`
    - :exc:`~.ClientException`
        - :exc:`~.commands.CommandRegistrationError`
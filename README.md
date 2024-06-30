# Discord Bot Development: Permissions Guide

## Overview

This guide provides a detailed explanation of the permission flags available for Discord bots. These permission flags are exported as `BigInt` values. Avoid converting them to numbers, as this may cause issues. Instead, use BigInts directly or use modules that support them.

## Permission Flags

Each permission flag allows specific actions within Discord servers. Below is a list of available permission flags and their descriptions:

### Channel-Specific Permissions

- **CreateInstantInvite**: Allows creation of instant invites.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly CreateInstantInvite: bigint;
    ```

- **ManageChannels**: Allows management and editing of channels.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly ManageChannels: bigint;
    ```

- **AddReactions**: Allows adding reactions to messages.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly AddReactions: bigint;
    ```

- **Stream**: Allows the user to go live.
  - Applies to: Voice, Stage channels
  - ```typescript
    readonly Stream: bigint;
    ```

- **ViewChannel**: Allows guild members to view a channel, read messages in text channels, and join voice channels.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly ViewChannel: bigint;
    ```

- **SendMessages**: Allows sending messages in a channel and creating threads in a forum (does not allow sending messages in threads).
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly SendMessages: bigint;
    ```

- **SendTTSMessages**: Allows sending of `/tts` messages.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly SendTTSMessages: bigint;
    ```

- **ManageMessages**: Allows deletion of other users' messages.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly ManageMessages: bigint;
    ```

- **EmbedLinks**: Links sent by users with this permission will be auto-embedded.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly EmbedLinks: bigint;
    ```

- **AttachFiles**: Allows uploading images and files.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly AttachFiles: bigint;
    ```

- **ReadMessageHistory**: Allows reading of message history.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly ReadMessageHistory: bigint;
    ```

- **MentionEveryone**: Allows using the `@everyone` tag to notify all users in a channel, and the `@here` tag to notify all online users in a channel.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly MentionEveryone: bigint;
    ```

- **UseExternalEmojis**: Allows using custom emojis from other servers.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly UseExternalEmojis: bigint;
    ```

### Guild-Wide Permissions

- **KickMembers**: Allows kicking members.
  - ```typescript
    readonly KickMembers: bigint;
    ```

- **BanMembers**: Allows banning members.
  - ```typescript
    readonly BanMembers: bigint;
    ```

- **Administrator**: Allows all permissions and bypasses channel permission overwrites.
  - ```typescript
    readonly Administrator: bigint;
    ```

- **ManageGuild**: Allows management and editing of the guild.
  - ```typescript
    readonly ManageGuild: bigint;
    ```

- **ViewAuditLog**: Allows viewing of audit logs.
  - ```typescript
    readonly ViewAuditLog: bigint;
    ```

- **PrioritySpeaker**: Allows using priority speaker in a voice channel.
  - Applies to: Voice channels
  - ```typescript
    readonly PrioritySpeaker: bigint;
    ```

- **ViewGuildInsights**: Allows viewing guild insights.
  - ```typescript
    readonly ViewGuildInsights: bigint;
    ```

- **ManageRoles**: Allows management and editing of roles.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly ManageRoles: bigint;
    ```

- **ManageWebhooks**: Allows management and editing of webhooks.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly ManageWebhooks: bigint;
    ```

- **ManageGuildExpressions**: Allows editing and deleting emojis, stickers, and soundboard sounds created by all users.
  - ```typescript
    readonly ManageGuildExpressions: bigint;
    ```

- **UseApplicationCommands**: Allows using application commands, including slash commands and context menu commands.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly UseApplicationCommands: bigint;
    ```

- **ManageEvents**: Allows editing and deleting scheduled events created by all users.
  - Applies to: Voice, Stage channels
  - ```typescript
    readonly ManageEvents: bigint;
    ```

- **ManageThreads**: Allows deleting and archiving threads, and viewing all private threads.
  - Applies to: Text channels
  - ```typescript
    readonly ManageThreads: bigint;
    ```

- **CreatePublicThreads**: Allows creating public and announcement threads.
  - Applies to: Text channels
  - ```typescript
    readonly CreatePublicThreads: bigint;
    ```

- **CreatePrivateThreads**: Allows creating private threads.
  - Applies to: Text channels
  - ```typescript
    readonly CreatePrivateThreads: bigint;
    ```

- **UseExternalStickers**: Allows using custom stickers from other servers.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly UseExternalStickers: bigint;
    ```

- **SendMessagesInThreads**: Allows sending messages in threads.
  - Applies to: Text channels
  - ```typescript
    readonly SendMessagesInThreads: bigint;
    ```

- **UseEmbeddedActivities**: Allows using Activities (applications with the `ApplicationFlags.Embedded` flag) in a voice channel.
  - Applies to: Voice channels
  - ```typescript
    readonly UseEmbeddedActivities: bigint;
    ```

- **ModerateMembers**: Allows timing out users to prevent them from sending or reacting to messages in chat and threads, and from speaking in voice and stage channels.
  - ```typescript
    readonly ModerateMembers: bigint;
    ```

- **ViewCreatorMonetizationAnalytics**: Allows viewing role subscription insights.
  - ```typescript
    readonly ViewCreatorMonetizationAnalytics: bigint;
    ```

- **UseSoundboard**: Allows using soundboard in a voice channel.
  - Applies to: Voice channels
  - ```typescript
    readonly UseSoundboard: bigint;
    ```

- **CreateGuildExpressions**: Allows creating emojis, stickers, and soundboard sounds, and editing and deleting those created by the current user.
  - ```typescript
    readonly CreateGuildExpressions: bigint;
    ```

- **CreateEvents**: Allows creating scheduled events, and editing and deleting those created by the current user.
  - Applies to: Voice, Stage channels
  - ```typescript
    readonly CreateEvents: bigint;
    ```

- **UseExternalSounds**: Allows using custom soundboard sounds from other servers.
  - Applies to: Voice channels
  - ```typescript
    readonly UseExternalSounds: bigint;
    ```

- **SendVoiceMessages**: Allows sending voice messages.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly SendVoiceMessages: bigint;
    ```

- **SendPolls**: Allows sending polls.
  - Applies to: Text, Voice, Stage channels
  - ```typescript
    readonly SendPolls: bigint;
    ```

## RESTError Structure

When interacting with Discord's REST API, you may encounter errors. The structure of a REST error response is as follows:

```typescript
export interface RESTError {
    code: number;
    message: string;
    errors?: RESTErrorData;
}
```

### RESTErrorFieldInformation

```typescript
export interface RESTErrorFieldInformation {
    code: string;
    message: string;
}
```

### RESTErrorGroupWrapper

```typescript
export interface RESTErrorGroupWrapper {
    _errors: RESTErrorData[];
}
```

### RESTErrorData

```typescript
export type RESTErrorData = RESTErrorFieldInformation | RESTErrorGroupWrapper | string | {
    [k: string]: RESTErrorData;
};
```

## Rate Limit Response Structure

When exceeding a rate limit, you will receive a rate limit response structured as follows:

```typescript
export interface RESTRateLimit {
    code?: number;           // Error code for some limits
    global: boolean;         // Indicates if you are being globally rate limited
    message: string;         // Message saying you are being rate limited
    retry_after: number;     // Number of seconds to wait before submitting another request
}
```

## LocalizationMap

The `LocalizationMap` type is used for localization purposes, mapping `LocaleString` to a localized string or null:

```typescript
export type LocalizationMap = Partial<Record<LocaleString, string | null>>;
```
